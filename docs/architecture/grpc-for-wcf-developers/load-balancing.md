---
title: 针对 WCF 开发人员的负载均衡 gRPC-gRPC
description: 选择要使用 gRPC services 的负载均衡器。
ms.date: 09/02/2019
ms.openlocfilehash: 215c0983146bbf9168f01956d64733f80cea6faf
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711164"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="d9bb3-103">负载均衡 gRPC</span><span class="sxs-lookup"><span data-stu-id="d9bb3-103">Load balancing gRPC</span></span>

<span data-ttu-id="d9bb3-104">GRPC 应用程序的典型部署包含多个相同的服务实例，提供复原能力和水平可扩展性。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="d9bb3-105">负载均衡将传入请求分布到这些实例上，以充分利用所有可用资源。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-105">Load balancing distributes incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="d9bb3-106">若要使此负载平衡对客户端不可见，通常使用代理负载均衡器服务器来处理来自客户端的请求，并将这些请求路由到后端实例。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="d9bb3-107">负载均衡器根据其运行的*层*进行分类。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="d9bb3-108">第4层负载均衡器适用于*传输*级别，例如，使用 TCP 套接字、连接和数据包。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections, and packets.</span></span> <span data-ttu-id="d9bb3-109">第7层负载均衡器在*应用程序*级别工作，专用于处理 gRPC 应用程序的 HTTP/2 请求。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="d9bb3-110">L4 负载均衡器</span><span class="sxs-lookup"><span data-stu-id="d9bb3-110">L4 load balancers</span></span>

<span data-ttu-id="d9bb3-111">L4 负载均衡器接受来自客户端的 TCP 连接请求，打开与某个后端实例的另一个连接，并在两个连接之间复制数据，无实际处理。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="d9bb3-112">L4 提供出色的性能和低延迟，但控制或智能非常少。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="d9bb3-113">只要客户端使连接保持打开状态，所有请求都将定向到相同的后端实例。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

 <span data-ttu-id="d9bb3-114">[Azure 负载均衡器](https://azure.microsoft.com/services/load-balancer/)是 L4 负载均衡器的一个示例。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-114">[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) is an example of an L4 load balancer.</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="d9bb3-115">L7 负载均衡器</span><span class="sxs-lookup"><span data-stu-id="d9bb3-115">L7 load balancers</span></span>

<span data-ttu-id="d9bb3-116">L7 负载均衡器分析传入的 HTTP/2 请求，并按请求将这些请求按请求传递到后端实例，无论客户端保持连接的时间长短。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="d9bb3-117">L7 负载均衡器的示例：</span><span class="sxs-lookup"><span data-stu-id="d9bb3-117">Examples of L7 load balancers:</span></span>

- [<span data-ttu-id="d9bb3-118">NGINX</span><span class="sxs-lookup"><span data-stu-id="d9bb3-118">NGINX</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="d9bb3-119">HAProxy</span><span class="sxs-lookup"><span data-stu-id="d9bb3-119">HAProxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="d9bb3-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="d9bb3-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="d9bb3-121">作为经验法则，L7 负载均衡器是 gRPC 和其他 HTTP/2 应用程序（事实上，对于 HTTP 应用程序）的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="d9bb3-122">L4 负载均衡器*适用*于 gRPC 应用程序，但在低延迟和低开销很重要时，它们主要非常有用。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-122">L4 load balancers will *work* with gRPC applications, but they're mainly useful when low latency and low overhead are important.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9bb3-123">撰写本文时，某些 L7 负载均衡器不支持 gRPC 服务所需的 HTTP/2 规范的所有部分，例如尾随标头。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-123">At the time of this writing, some L7 load balancers don't support all the parts of the HTTP/2 specification that are required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="d9bb3-124">如果使用的是 TLS 加密，负载均衡器可以终止 TLS 连接并将未加密的请求传递到后端应用程序，也可以传递加密的请求。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-124">If you're using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or they can pass the encrypted request along.</span></span> <span data-ttu-id="d9bb3-125">无论采用哪种方式，都需要将负载均衡器配置为具有服务器的公钥和私钥，使其可以解密处理请求。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-125">Either way, the load balancer will need to be configured with the server's public and private key so it can decrypt requests for processing.</span></span>

<span data-ttu-id="d9bb3-126">请参阅你喜欢的负载均衡器的文档，了解如何将其配置为通过后端服务处理 HTTP/2 请求。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-126">See to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="d9bb3-127">Kubernetes 中的负载均衡</span><span class="sxs-lookup"><span data-stu-id="d9bb3-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="d9bb3-128">有关 Kubernetes 上内部服务之间的负载平衡的讨论，请参阅[服务网格部分](service-mesh.md)。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-128">See [the section on service meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d9bb3-129">[上一页](service-mesh.md)
>[下一页](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="d9bb3-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
