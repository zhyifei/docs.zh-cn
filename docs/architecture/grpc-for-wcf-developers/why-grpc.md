---
title: 为什么建议为 WCF 开发人员使用 gRPC-gRPC for WCF 开发人员
description: 讨论为什么 gRPC 非常适合要迁移到现代体系结构和平台的 WCF 开发人员。
ms.date: 09/02/2019
ms.openlocfilehash: da712e1ceee92f0a1a2661252dcda602f5dde9a0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966948"
---
# <a name="why-grpc-is-recommended-for-wcf-developers"></a><span data-ttu-id="9e368-103">为什么向 WCF 开发人员推荐 gRPC</span><span class="sxs-lookup"><span data-stu-id="9e368-103">Why gRPC is recommended for WCF developers</span></span>

<span data-ttu-id="9e368-104">在深入探讨 gRPC 的语言和技术之前，有必要讨论为什么 gRPC 是适用于要迁移到 .NET Core 的 WCF 开发人员的正确解决方案，但前提是有可用的替代方法。</span><span class="sxs-lookup"><span data-stu-id="9e368-104">Before diving deeply into the language and techniques of gRPC, it's worth discussing why gRPC is the right solution for WCF developers who want to migrate to .NET Core, given there are alternatives available.</span></span>

## <a name="similarity-to-wcf"></a><span data-ttu-id="9e368-105">与 WCF 的相似性</span><span class="sxs-lookup"><span data-stu-id="9e368-105">Similarity to WCF</span></span>

<span data-ttu-id="9e368-106">尽管其实现和方式不同，但使用 gRPC 开发和使用服务的实际经验对于 WCF 开发人员来说都应该非常直观。</span><span class="sxs-lookup"><span data-stu-id="9e368-106">Although its implementation and approach is different, the actual experience of developing and consuming services with gRPC should be very intuitive for WCF developers.</span></span> <span data-ttu-id="9e368-107">使代码可以像客户端和服务器相同的平台上，而无需担心网络的基本目标是相同的。</span><span class="sxs-lookup"><span data-stu-id="9e368-107">The underlying goal of making it possible to code as though the client and server were on the same platform, without needing to worry about networking, is the same.</span></span> <span data-ttu-id="9e368-108">这两个平台共享声明并实现接口的原则，即使用于声明该接口的过程不同。</span><span class="sxs-lookup"><span data-stu-id="9e368-108">Both platforms share the principle of declaring and then implementing an interface, even though the process for declaring that interface is different.</span></span> <span data-ttu-id="9e368-109">你将在第5章中看到，gRPC 映射的不同类型的 RPC 调用非常适合 WCF 服务可用的不同绑定。</span><span class="sxs-lookup"><span data-stu-id="9e368-109">And as you'll see in chapter 5, the different types of RPC calls supported by gRPC map very well to the different bindings available to WCF services.</span></span>

## <a name="benefits-of-grpc"></a><span data-ttu-id="9e368-110">GRPC 的优点</span><span class="sxs-lookup"><span data-stu-id="9e368-110">Benefits of gRPC</span></span>

<span data-ttu-id="9e368-111">GRPC 在其他解决方案上出现的其他原因包括：</span><span class="sxs-lookup"><span data-stu-id="9e368-111">Additional reasons why gRPC stands above other solutions are:</span></span>

### <a name="performance"></a><span data-ttu-id="9e368-112">性能</span><span class="sxs-lookup"><span data-stu-id="9e368-112">Performance</span></span>

<span data-ttu-id="9e368-113">正如前面所讨论的，使用 HTTP/2 而不是 HTTP/1.1 不再要求用户可读的消息，而是使用更快的更快的二进制协议。</span><span class="sxs-lookup"><span data-stu-id="9e368-113">As already discussed, using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller faster binary protocol.</span></span> <span data-ttu-id="9e368-114">这更有效率于计算机进行分析。</span><span class="sxs-lookup"><span data-stu-id="9e368-114">This is more efficient for computers to parse.</span></span> <span data-ttu-id="9e368-115">HTTP/2 还支持通过单一连接发送多路复用请求，从而在无需在队列中等待的情况下立即发送响应（HTTP/1.1 中的问题称为 "行式（逾越）阻塞"）。</span><span class="sxs-lookup"><span data-stu-id="9e368-115">HTTP/2 also supports multiplexing requests over a single connection enabling responses to be sent as soon as they're ready without the need to wait in a queue (an issue in HTTP/1.1 known as "head-of-line (HOL) blocking").</span></span> <span data-ttu-id="9e368-116">使用 gRPC 时需要更少的资源，这使其成为适用于移动设备和速度较慢的网络的良好解决方案。</span><span class="sxs-lookup"><span data-stu-id="9e368-116">Fewer resources are needed when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.</span></span>

### <a name="interoperability"></a><span data-ttu-id="9e368-117">互操作性</span><span class="sxs-lookup"><span data-stu-id="9e368-117">Interoperability</span></span>

<span data-ttu-id="9e368-118">对于所有主要编程语言和平台（包括 .NET、Java、Python、中转、 C++Node.js、Swift、Dart、RUBY 和 PHP），都有一些 gRPC 的工具和库。</span><span class="sxs-lookup"><span data-stu-id="9e368-118">There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP.</span></span> <span data-ttu-id="9e368-119">由于协议缓冲区的二进制网络格式和每个平台的有效代码生成，开发人员可以构建具有高性能的应用程序，同时仍享有完全的跨平台支持。</span><span class="sxs-lookup"><span data-stu-id="9e368-119">Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.</span></span>

### <a name="usability-and-productivity"></a><span data-ttu-id="9e368-120">可用性和生产力</span><span class="sxs-lookup"><span data-stu-id="9e368-120">Usability and productivity</span></span>

<span data-ttu-id="9e368-121">gRPC 是一个综合性 RPC 解决方案。</span><span class="sxs-lookup"><span data-stu-id="9e368-121">gRPC is a comprehensive RPC solution.</span></span> <span data-ttu-id="9e368-122">它在多个语言和平台之间保持一致，并提供出色的工具，其中包含自动生成的很多必需的样板代码，因此，更多的开发人员时间将侧重于业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="9e368-122">It works consistently across multiple languages and platforms, and provides excellent tooling, with much of the necessary boilerplate code auto-generated, so more developer time is freed up to focus on business logic.</span></span>

### <a name="streaming"></a><span data-ttu-id="9e368-123">流式处理</span><span class="sxs-lookup"><span data-stu-id="9e368-123">Streaming</span></span>

<span data-ttu-id="9e368-124">gRPC 具有完全双向流式处理，它为 WCF 的全双工服务提供非常类似的功能。</span><span class="sxs-lookup"><span data-stu-id="9e368-124">gRPC has full bidirectional streaming, which provides very similar functionality to WCF's full duplex services.</span></span> <span data-ttu-id="9e368-125">gRPC 流式处理可通过常规 internet 连接、负载均衡器和服务网格运行。</span><span class="sxs-lookup"><span data-stu-id="9e368-125">gRPC streaming can operate over regular internet connections, load balancers, and service meshes.</span></span>

### <a name="deadlinetimeouts-and-cancellation"></a><span data-ttu-id="9e368-126">截止时间/超时和取消</span><span class="sxs-lookup"><span data-stu-id="9e368-126">Deadline/timeouts and cancellation</span></span>

<span data-ttu-id="9e368-127">gRPC 允许客户端指定 RPC 完成的最长时间。</span><span class="sxs-lookup"><span data-stu-id="9e368-127">gRPC allows clients to specify a maximum time for an RPC to complete.</span></span> <span data-ttu-id="9e368-128">如果超过指定的截止时间，则服务器可以独立于客户端取消该操作。</span><span class="sxs-lookup"><span data-stu-id="9e368-128">If the specified deadline is exceeded the server can cancel the operation independently of the client.</span></span> <span data-ttu-id="9e368-129">截止时间和取消可通过进一步的 gRPC 调用进行传播，以帮助强制实施资源使用限制。</span><span class="sxs-lookup"><span data-stu-id="9e368-129">Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits.</span></span> <span data-ttu-id="9e368-130">超过截止时间时，客户端也可能会中止操作（例如，由于用户交互）。</span><span class="sxs-lookup"><span data-stu-id="9e368-130">Clients may also abort operations when a deadline is exceeded, or earlier if necessary (e.g. due to a user interaction).</span></span>

### <a name="security"></a><span data-ttu-id="9e368-131">安全性</span><span class="sxs-lookup"><span data-stu-id="9e368-131">Security</span></span>

<span data-ttu-id="9e368-132">在 TLS 端到端加密连接上使用 HTTP/2 时，gRPC 是隐式的。</span><span class="sxs-lookup"><span data-stu-id="9e368-132">gRPC is implicitly secure when using HTTP/2 over an TLS end-to-end encrypted connection.</span></span> <span data-ttu-id="9e368-133">支持客户端证书身份验证（请参阅第6章），进一步提高客户端和服务器之间的安全性和信任。</span><span class="sxs-lookup"><span data-stu-id="9e368-133">Support for Client Certificate authentication (see chapter 6) further increases security and trust between client and server.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9e368-134">[上一页](network-protocols.md)
>[下一页](protocol-buffers.md)</span><span class="sxs-lookup"><span data-stu-id="9e368-134">[Previous](network-protocols.md)
[Next](protocol-buffers.md)</span></span>
