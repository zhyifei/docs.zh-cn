---
title: 为什么我们为 WCF 开发人员推荐 gRPC - gRPC 面向 WCF 开发人员
description: 讨论 gRPC 为什么非常适合想要迁移到现代体系结构和平台的 WCF 开发人员。
ms.date: 09/02/2019
ms.openlocfilehash: 664781e94c24c1796eafa6a70eb28d453b530d66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147641"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a><span data-ttu-id="b5ebe-103">我们为什么建议适用于 WCF 开发人员的 gRPC</span><span class="sxs-lookup"><span data-stu-id="b5ebe-103">Why we recommend gRPC for WCF developers</span></span>

<span data-ttu-id="b5ebe-104">在我们深入探讨 gRPC 的语言和技术之前，值得讨论为什么 gRPC 是 Windows 通信基础 （WCF） 开发人员想要迁移到 .NET Core 的正确解决方案。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-104">Before we dive deeply into the language and techniques of gRPC, it's worth discussing why gRPC is the right solution for Windows Communication Foundation (WCF) developers who want to migrate to .NET Core.</span></span>

## <a name="similarity-to-wcf"></a><span data-ttu-id="b5ebe-105">与 WCF 的相似性</span><span class="sxs-lookup"><span data-stu-id="b5ebe-105">Similarity to WCF</span></span>

<span data-ttu-id="b5ebe-106">尽管 gRPC 的实现和方法不同，但使用 gRPC 开发和使用服务的经验对于 WCF 开发人员来说应该是直观的。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-106">Although the implementation and approach are different for gRPC, the experience of developing and consuming services with gRPC should be intuitive for WCF developers.</span></span> <span data-ttu-id="b5ebe-107">基本目标是相同的：使客户端和服务器位于同一平台上，无需担心网络，可以编写代码。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-107">The underlying goal is the same: make it possible to code as though the client and server are on the same platform, without needing to worry about networking.</span></span>

<span data-ttu-id="b5ebe-108">两个平台共享声明然后实现接口的原则，即使声明该接口的过程是不同的。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-108">Both platforms share the principle of declaring and then implementing an interface, even though the process for declaring that interface is different.</span></span> <span data-ttu-id="b5ebe-109">正如您将在第 5 章中看到的，gRPC 支持的不同类型的 RPC 调用很好地映射到 WCF 服务可用的绑定。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-109">And as you'll see in chapter 5, the different types of RPC calls that gRPC supports map well to the bindings available to WCF services.</span></span>

## <a name="benefits-of-grpc"></a><span data-ttu-id="b5ebe-110">gRPC 的好处</span><span class="sxs-lookup"><span data-stu-id="b5ebe-110">Benefits of gRPC</span></span>

<span data-ttu-id="b5ebe-111">gRPC 高于其他解决方案，原因如下。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-111">gRPC stands above other solutions for the following reasons.</span></span>

### <a name="performance"></a><span data-ttu-id="b5ebe-112">性能</span><span class="sxs-lookup"><span data-stu-id="b5ebe-112">Performance</span></span>

<span data-ttu-id="b5ebe-113">使用 HTTP/2 而不是 HTTP/1.1 可消除对人可读消息的要求，而是使用更小、更快的二进制协议。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-113">Using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller, faster binary protocol.</span></span> <span data-ttu-id="b5ebe-114">这对计算机进行分析的效率更高。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-114">This is more efficient for computers to parse.</span></span> <span data-ttu-id="b5ebe-115">HTTP/2 还支持通过单个连接进行多路复用请求。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-115">HTTP/2 also supports multiplexing requests over a single connection.</span></span> <span data-ttu-id="b5ebe-116">此支持允许在响应准备就绪后立即发送，而无需在队列中等待。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-116">This support enables responses to be sent as soon as they're ready without the need to wait in a queue.</span></span> <span data-ttu-id="b5ebe-117">（在 HTTP/1.1 中，此问题称为"线头 （HOL） 阻塞"。使用 gRPC 时需要的资源更少，这使得它成为用于移动设备和速度较慢的网络的良好解决方案。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-117">(In HTTP/1.1, this issue is known as "head-of-line (HOL) blocking.") You need fewer resources when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.</span></span>

### <a name="interoperability"></a><span data-ttu-id="b5ebe-118">互操作性</span><span class="sxs-lookup"><span data-stu-id="b5ebe-118">Interoperability</span></span>

<span data-ttu-id="b5ebe-119">所有主要编程语言和平台都有 gRPC 工具和库，包括 .NET、Java、Python、Go、C++、Node.js、Swift、Dart、Ruby 和 PHP。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-119">There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP.</span></span> <span data-ttu-id="b5ebe-120">得益于协议缓冲区二进制线格式和每个平台的有效代码生成，开发人员可以构建执行应用程序，同时仍然享受全面的跨平台支持。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-120">Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.</span></span>

### <a name="usability-and-productivity"></a><span data-ttu-id="b5ebe-121">易用性和工作效率</span><span class="sxs-lookup"><span data-stu-id="b5ebe-121">Usability and productivity</span></span>

<span data-ttu-id="b5ebe-122">gRPC 是一个全面的 RPC 解决方案。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-122">gRPC is a comprehensive RPC solution.</span></span> <span data-ttu-id="b5ebe-123">它在多种语言和平台上一致工作。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-123">It works consistently across multiple languages and platforms.</span></span> <span data-ttu-id="b5ebe-124">它还提供了出色的工具，自动生成许多必要的样板代码。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-124">It also provides excellent tooling, with much of the necessary boilerplate code automatically generated.</span></span> <span data-ttu-id="b5ebe-125">因此，可以腾出更多开发人员时间来关注业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-125">So more developer time is freed up to focus on business logic.</span></span>

### <a name="streaming"></a><span data-ttu-id="b5ebe-126">流式处理</span><span class="sxs-lookup"><span data-stu-id="b5ebe-126">Streaming</span></span>

<span data-ttu-id="b5ebe-127">gRPC 具有完全双向流式处理，提供与 WCF 全双工服务类似的功能。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-127">gRPC has full bidirectional streaming, which provides similar functionality to WCF's full duplex services.</span></span> <span data-ttu-id="b5ebe-128">gRPC 流可以通过常规互联网连接、负载均衡器和服务联结运行。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-128">gRPC streaming can operate over regular internet connections, load balancers, and service meshes.</span></span>

### <a name="deadlinetimeouts-and-cancellation"></a><span data-ttu-id="b5ebe-129">截止日期/超时和取消</span><span class="sxs-lookup"><span data-stu-id="b5ebe-129">Deadline/timeouts and cancellation</span></span>

<span data-ttu-id="b5ebe-130">gRPC 允许客户端指定 RPC 完成的最大时间。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-130">gRPC allows clients to specify a maximum time for an RPC to finish.</span></span> <span data-ttu-id="b5ebe-131">如果超过指定的截止时间，服务器可以独立于客户端取消操作。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-131">If the specified deadline is exceeded, the server can cancel the operation independently of the client.</span></span> <span data-ttu-id="b5ebe-132">截止和取消可以通过进一步的 gRPC 调用传播，以帮助强制实施资源使用限制。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-132">Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits.</span></span> <span data-ttu-id="b5ebe-133">客户端也可以在超过截止时间时停止操作，或者在必要时更早停止操作（例如，由于用户交互）。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-133">Clients can also stop operations when a deadline is exceeded, or earlier if necessary (for example, because of a user interaction).</span></span>

### <a name="security"></a><span data-ttu-id="b5ebe-134">安全性</span><span class="sxs-lookup"><span data-stu-id="b5ebe-134">Security</span></span>

<span data-ttu-id="b5ebe-135">gRPC 在 TLS 端到端加密连接上使用 HTTP/2 时具有隐式安全。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-135">gRPC is implicitly secure when it's using HTTP/2 over a TLS end-to-end encrypted connection.</span></span> <span data-ttu-id="b5ebe-136">对客户端证书身份验证的支持（参见[第 6 章](security.md)）进一步增强了客户端和服务器之间的安全性和信任。</span><span class="sxs-lookup"><span data-stu-id="b5ebe-136">Support for client certificate authentication (see [chapter 6](security.md)) further increases security and trust between client and server.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b5ebe-137">[上一个](network-protocols.md)
>[下一个](protocol-buffers.md)</span><span class="sxs-lookup"><span data-stu-id="b5ebe-137">[Previous](network-protocols.md)
[Next](protocol-buffers.md)</span></span>
