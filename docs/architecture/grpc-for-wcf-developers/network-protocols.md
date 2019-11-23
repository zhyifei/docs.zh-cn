---
title: 网络协议-适用于 WCF 开发人员的 gRPC
description: GRPC 网络协议的概述。
ms.date: 09/02/2019
ms.openlocfilehash: 5e837738bd345608ca7119d04c9221acb220c276
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971706"
---
# <a name="network-protocols"></a><span data-ttu-id="e5465-103">网络协议</span><span class="sxs-lookup"><span data-stu-id="e5465-103">Network protocols</span></span>

<span data-ttu-id="e5465-104">与 WCF 不同，gRPC 使用 HTTP/2 作为其网络的基础。</span><span class="sxs-lookup"><span data-stu-id="e5465-104">Unlike WCF, gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="e5465-105">这与 WCF 和 SOAP 相比具有明显的优势，后者仅在 HTTP/1.1 上操作。</span><span class="sxs-lookup"><span data-stu-id="e5465-105">This offers significant advantages over WCF and SOAP, which only operate on HTTP/1.1.</span></span> <span data-ttu-id="e5465-106">对于想要使用 gRPC 的开发人员，如果没有 HTTP/2 的替代方法，则更详细地探究 HTTP/2，并识别使用 gRPC 的其他优点。</span><span class="sxs-lookup"><span data-stu-id="e5465-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits to using gRPC.</span></span>

<span data-ttu-id="e5465-107">HTTP/2 （由2015中的 Internet 工程任务组发布）派生自 Google 已在使用的实验 SPDY 协议。</span><span class="sxs-lookup"><span data-stu-id="e5465-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="e5465-108">它经过专门设计，比 HTTP/1.1 更高效、更快、更安全。</span><span class="sxs-lookup"><span data-stu-id="e5465-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="e5465-109">HTTP/2 的主要功能</span><span class="sxs-lookup"><span data-stu-id="e5465-109">Key features of HTTP/2</span></span>

<span data-ttu-id="e5465-110">以下列表显示了 HTTP/2 的一些主要功能和优势：</span><span class="sxs-lookup"><span data-stu-id="e5465-110">The following list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="e5465-111">二进制协议</span><span class="sxs-lookup"><span data-stu-id="e5465-111">Binary protocol</span></span>

<span data-ttu-id="e5465-112">请求/响应周期不再需要文本命令。</span><span class="sxs-lookup"><span data-stu-id="e5465-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="e5465-113">这可以简化和加速命令的实现。</span><span class="sxs-lookup"><span data-stu-id="e5465-113">This simplifies and speeds up implementation of commands.</span></span> <span data-ttu-id="e5465-114">具体而言，分析数据的速度更快，使用的内存更少，网络延迟会因速度的明显相关改进而降低，同时还能提供更好的网络资源。</span><span class="sxs-lookup"><span data-stu-id="e5465-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="e5465-115">流</span><span class="sxs-lookup"><span data-stu-id="e5465-115">Streams</span></span>

<span data-ttu-id="e5465-116">流允许在发送方和接收方之间创建生存期较长的连接，通过这些连接可以异步发送多个消息或帧。</span><span class="sxs-lookup"><span data-stu-id="e5465-116">Streams allow for the creation of long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="e5465-117">多个流可以独立于单个 HTTP/2 连接进行操作。</span><span class="sxs-lookup"><span data-stu-id="e5465-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="e5465-118">通过单个 TCP 连接请求多路复用</span><span class="sxs-lookup"><span data-stu-id="e5465-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="e5465-119">此功能是 HTTP/2 最重要的一项创新。</span><span class="sxs-lookup"><span data-stu-id="e5465-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="e5465-120">通过允许对数据进行多次并行请求，现在可以从一台服务器同时下载 web 文件。</span><span class="sxs-lookup"><span data-stu-id="e5465-120">By allowing multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="e5465-121">网站加载速度更快，需要进行优化。</span><span class="sxs-lookup"><span data-stu-id="e5465-121">Websites load faster and the need for optimization is reduced.</span></span> <span data-ttu-id="e5465-122">已准备就绪的标头（逾越）阻塞，在之前的请求完成之前，必须等待发送响应（尽管在 TCP 传输级别仍可能出现闭锁阻塞）。</span><span class="sxs-lookup"><span data-stu-id="e5465-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="e5465-123">类似于 Wcf-nettcp 的性能，跨平台</span><span class="sxs-lookup"><span data-stu-id="e5465-123">NetTCP-like performance, cross-platform</span></span>

<span data-ttu-id="e5465-124">从根本上讲，gRPC 和 HTTP/2 的组合为开发人员提供了与 WCF 的 Wcf-nettcp 绑定相同的速度和效率，在某些情况下，其速度更快，效率更高。</span><span class="sxs-lookup"><span data-stu-id="e5465-124">Fundamentally, the combination of gRPC and HTTP/2 offer developers at least the equivalent speed and efficiency of NetTCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="e5465-125">但是，与 Wcf-nettcp 不同，gRPC over HTTP/2 不会限制为 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5465-125">However, unlike NetTCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e5465-126">[上一页](interface-definition-language.md)
>[下一页](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="e5465-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
