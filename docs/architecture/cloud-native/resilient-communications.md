---
title: 可复原通信
description: 构建适用于 Azure 的云本机 .NET 应用 |弹性通信
ms.date: 06/30/2019
ms.openlocfilehash: 324f5426af1c892db73aa6fc2336a19b7a8e499e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "73841221"
---
# <a name="resilient-communications"></a><span data-ttu-id="25109-103">弹性通信</span><span class="sxs-lookup"><span data-stu-id="25109-103">Resilient communications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="25109-104">在本指南中，我们已 evangelized 了超越传统的单一应用程序设计并使用基于微服务的体系结构，在该体系结构中，一组分布式、独立服务独立运行并与每个服务通信其他使用标准通信协议，例如 HTTP 和 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="25109-104">Throughout this book, we've evangelized the merits of moving beyond traditional monolithic application design and embracing a microservice-based architecture where a set of distributed, self-contained services run independently and communicate with each other using standard communication protocols such as HTTP and HTTPS.</span></span> <span data-ttu-id="25109-105">尽管此类体系结构会为你提供许多重要的好处，但它也带来了许多挑战。</span><span class="sxs-lookup"><span data-stu-id="25109-105">While such an architecture buys you many important benefits, it also presents many challenges.</span></span> <span data-ttu-id="25109-106">例如，请考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="25109-106">Consider, for example, the following concerns:</span></span>

- <span data-ttu-id="25109-107">*进程外网络通信。*</span><span class="sxs-lookup"><span data-stu-id="25109-107">*Out-of-process network communication.*</span></span> <span data-ttu-id="25109-108">每个服务通过网络协议进行通信，该协议引入了网络拥塞、延迟和暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="25109-108">Each service communicates over a network protocol that introduces network congestion, latency, and transient faults.</span></span>
- <span data-ttu-id="25109-109">*服务发现。*</span><span class="sxs-lookup"><span data-stu-id="25109-109">*Service discovery.*</span></span> <span data-ttu-id="25109-110">每个服务都在使用其自己的 IP 地址和端口的计算机群集上运行，服务如何彼此发现并相互通信？</span><span class="sxs-lookup"><span data-stu-id="25109-110">With each service running across a cluster of machines with its own IP address and port, how do services discover and communicate with each other?</span></span>
- <span data-ttu-id="25109-111">*复原.*</span><span class="sxs-lookup"><span data-stu-id="25109-111">*Resiliency.*</span></span> <span data-ttu-id="25109-112">如何管理短暂的故障并使系统保持稳定？</span><span class="sxs-lookup"><span data-stu-id="25109-112">How do you manage short-lived failures and keep the system stable?</span></span>
- <span data-ttu-id="25109-113">*负载均衡。*</span><span class="sxs-lookup"><span data-stu-id="25109-113">*Load balancing.*</span></span> <span data-ttu-id="25109-114">如何将入站流量分布到多个服务实例？</span><span class="sxs-lookup"><span data-stu-id="25109-114">How does inbound traffic get distributed across multiple instances of a service?</span></span>
- <span data-ttu-id="25109-115">*安全性。*</span><span class="sxs-lookup"><span data-stu-id="25109-115">*Security.*</span></span> <span data-ttu-id="25109-116">安全问题（例如传输级加密和证书管理）如何强制实施？</span><span class="sxs-lookup"><span data-stu-id="25109-116">How are security concerns such as transport-level encryption and certificate management enforced?</span></span>
- <span data-ttu-id="25109-117">*分布式监视。*</span><span class="sxs-lookup"><span data-stu-id="25109-117">*Distributed Monitoring.*</span></span> <span data-ttu-id="25109-118">-你如何跨多个使用服务的单个请求关联和捕获可跟踪性和监视？</span><span class="sxs-lookup"><span data-stu-id="25109-118">- How do you correlate and capture traceability and monitoring for a single request across multiple consuming services?</span></span>

<span data-ttu-id="25109-119">尽管可以使用各种库和框架来解决这些问题，但在代码库中实现它们可能会消耗大量资源、复杂且耗时。</span><span class="sxs-lookup"><span data-stu-id="25109-119">While these concerns can be addressed with various libraries and frameworks, implementing them inside your codebase can be expensive, complex, and time-consuming.</span></span> <span data-ttu-id="25109-120">而且，最终会出现一个解决方案，其中基础结构问题与业务逻辑耦合在一起。</span><span class="sxs-lookup"><span data-stu-id="25109-120">Moreover, you end up with a solution where infrastructure concerns are coupled to business logic.</span></span>

## <a name="service-mesh"></a><span data-ttu-id="25109-121">服务网格</span><span class="sxs-lookup"><span data-stu-id="25109-121">Service mesh</span></span>

<span data-ttu-id="25109-122">更好的方法是，考虑一种新的、快速发展的技术，该技术以*服务网格*为依据。</span><span class="sxs-lookup"><span data-stu-id="25109-122">A better approach is to consider a new and rapidly evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="25109-123">[服务网格](https://www.nginx.com/blog/what-is-a-service-mesh/)是一种可配置的基础结构层，其中内置了用于处理服务通信的功能和上面提到的许多挑战。</span><span class="sxs-lookup"><span data-stu-id="25109-123">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service communication and many of the challenges mentioned above.</span></span> <span data-ttu-id="25109-124">它将这些问题从业务代码中分离出来，并将其移到服务代理（每个服务附带的实例）中。</span><span class="sxs-lookup"><span data-stu-id="25109-124">It decouples these concerns from your business code and moves them into a service proxy, an instance of which accompanies each of your services.</span></span> <span data-ttu-id="25109-125">服务网格代理通常称为[挎斗模式](https://docs.microsoft.com/azure/architecture/patterns/sidecar)，可将其部署到单独的进程中，以提供业务代码的隔离和封装。</span><span class="sxs-lookup"><span data-stu-id="25109-125">Often referred to as the [Sidecar pattern](https://docs.microsoft.com/azure/architecture/patterns/sidecar), the service mesh proxy is deployed into a separate process to provide isolation and encapsulation from your business code.</span></span> <span data-ttu-id="25109-126">但是，该代理与正在创建的服务以及共享其生命周期的方法密切相关。</span><span class="sxs-lookup"><span data-stu-id="25109-126">However, the proxy is closely linked to the service being created along with it and sharing its lifecycle.</span></span> <span data-ttu-id="25109-127">图6-9 显示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="25109-127">Figure 6-9 shows this scenario.</span></span>

![使用侧面汽车的服务网格](./media/service-mesh-with-side-car.png)

<span data-ttu-id="25109-129">图 6-9。</span><span class="sxs-lookup"><span data-stu-id="25109-129">**Figure 6-9**.</span></span> <span data-ttu-id="25109-130">使用侧面汽车的服务网格</span><span class="sxs-lookup"><span data-stu-id="25109-130">Service mesh with a side car</span></span>

<span data-ttu-id="25109-131">在上图中，请注意代理如何截获和管理微服务与群集之间的通信。</span><span class="sxs-lookup"><span data-stu-id="25109-131">In the previous figure, note how the proxy intercepts and manages communication among the microservices and the cluster.</span></span>

<span data-ttu-id="25109-132">服务网格以逻辑方式拆分为两个不同的组件：[数据平面](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc)和[控制平面](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc)。</span><span class="sxs-lookup"><span data-stu-id="25109-132">A service mesh is logically split into two disparate components: A [data plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) and [control plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span></span> <span data-ttu-id="25109-133">图6-10 显示了这些组件及其责任。</span><span class="sxs-lookup"><span data-stu-id="25109-133">Figure 6-10 shows these components and their responsibilities.</span></span>

![服务网格控制和数据平面](./media/istio-control-and-data-plane.png)

<span data-ttu-id="25109-135">**图6-10。**</span><span class="sxs-lookup"><span data-stu-id="25109-135">**Figure 6-10.**</span></span> <span data-ttu-id="25109-136">服务网格控制和数据平面</span><span class="sxs-lookup"><span data-stu-id="25109-136">Service mesh control and data plane</span></span>

<span data-ttu-id="25109-137">一旦配置后，服务网格就会非常有效。</span><span class="sxs-lookup"><span data-stu-id="25109-137">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="25109-138">它可以从服务发现终结点中检索相应的实例池。</span><span class="sxs-lookup"><span data-stu-id="25109-138">It can retrieve a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="25109-139">然后，它可以将请求发送到特定的实例，记录结果的延迟和响应类型。</span><span class="sxs-lookup"><span data-stu-id="25109-139">It can then send a request to a specific instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="25109-140">网格可以根据许多因素选择最有可能返回快速响应的实例，包括其观察到的最近请求的延迟。</span><span class="sxs-lookup"><span data-stu-id="25109-140">A mesh can choose the instance most likely to return a fast response based on many factors, including its observed latency for recent requests.</span></span>

<span data-ttu-id="25109-141">如果实例无响应或失败，网格可以在另一个实例上重试该请求。</span><span class="sxs-lookup"><span data-stu-id="25109-141">If an instance is unresponsive or fails, the mesh can retry the request on another instance.</span></span> <span data-ttu-id="25109-142">如果池总是返回错误，则网格可以将其从负载平衡池中逐出，以后在修复后定期重试。</span><span class="sxs-lookup"><span data-stu-id="25109-142">If a pool consistently returns errors, a mesh can evict it from the load-balancing pool to be retried periodically later after it heals.</span></span> <span data-ttu-id="25109-143">如果请求超时，网格可能会失败，然后重试该请求。</span><span class="sxs-lookup"><span data-stu-id="25109-143">If a request times out, a mesh can fail and then retry the request.</span></span> <span data-ttu-id="25109-144">网格以度量值和分布式跟踪的形式捕获行为，然后可以将其发送到集中式指标系统。</span><span class="sxs-lookup"><span data-stu-id="25109-144">A mesh captures behavior in the form of metrics and distributed tracing, which then can be emitted to a centralized metrics system.</span></span>

## <a name="istio-and-envoy"></a><span data-ttu-id="25109-145">Istio 和 Envoy</span><span class="sxs-lookup"><span data-stu-id="25109-145">Istio and Envoy</span></span>

<span data-ttu-id="25109-146">虽然目前存在一些服务网格选项，但在撰写本文的时候， [Istio](https://istio.io/docs/concepts/what-is-istio/)是最常用的。</span><span class="sxs-lookup"><span data-stu-id="25109-146">While a few service mesh options currently exist, [Istio](https://istio.io/docs/concepts/what-is-istio/) is the most popular as of the time of this writing.</span></span> <span data-ttu-id="25109-147">这是一种可集成到新的或现有的分布式应用程序中的开源产品，来自 IBM、Google 和 Lyft 的合作。</span><span class="sxs-lookup"><span data-stu-id="25109-147">A joint venture from IBM, Google, and Lyft, it's an open-source offering that can be integrated into a new or existing distributed application.</span></span> <span data-ttu-id="25109-148">它提供一致的完整解决方案来保护、连接和监视微服务。</span><span class="sxs-lookup"><span data-stu-id="25109-148">It provides a consistent and complete solution to secure, connect, and monitor microservices.</span></span> <span data-ttu-id="25109-149">其功能包括：</span><span class="sxs-lookup"><span data-stu-id="25109-149">Its features include:</span></span>

- <span data-ttu-id="25109-150">使用基于标识的强身份验证和授权在群集中保护服务间通信。</span><span class="sxs-lookup"><span data-stu-id="25109-150">Secure service-to-service communication in a cluster with strong identity-based authentication and authorization.</span></span>
- <span data-ttu-id="25109-151">自动负载均衡，适用于 HTTP、 [gRPC](https://grpc.io/)、WEBSOCKET 和 TCP 流量。</span><span class="sxs-lookup"><span data-stu-id="25109-151">Automatic load balancing for HTTP, [gRPC](https://grpc.io/), WebSocket, and TCP traffic.</span></span>
- <span data-ttu-id="25109-152">通过丰富的路由规则、重试、故障转移和故障注入对流量行为进行精细控制。</span><span class="sxs-lookup"><span data-stu-id="25109-152">Fine-grained control of traffic behavior with rich routing rules, retries, failovers, and fault injection.</span></span>
- <span data-ttu-id="25109-153">支持访问控制、速率限制和配额的可插入策略层和配置 API。</span><span class="sxs-lookup"><span data-stu-id="25109-153">A pluggable policy layer and configuration API supporting access controls, rate limits, and quotas.</span></span>
- <span data-ttu-id="25109-154">针对群集中的所有流量（包括流入和出口）的自动指标、日志和跟踪。</span><span class="sxs-lookup"><span data-stu-id="25109-154">Automatic metrics, logs, and traces for all traffic within a cluster, including cluster ingress and egress.</span></span>

<span data-ttu-id="25109-155">Istio 实现的关键组件是一种名为[Envoy 代理](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)的代理服务。</span><span class="sxs-lookup"><span data-stu-id="25109-155">A key component for an Istio implementation is a proxy service entitled the [Envoy proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span></span> <span data-ttu-id="25109-156">从 Lyft 开始，到[云本机计算基础](https://www.cncf.io/)（在第1章讨论），Envoy 代理与每个服务一起运行，并为以下功能提供平台无关的基础：</span><span class="sxs-lookup"><span data-stu-id="25109-156">Originating from Lyft and subsequently contributed to the [Cloud Native Computing Foundation](https://www.cncf.io/) (discussed in chapter 1), the Envoy proxy runs alongside each service and provides a platform-agnostic foundation for the following features:</span></span>

- <span data-ttu-id="25109-157">动态服务发现。</span><span class="sxs-lookup"><span data-stu-id="25109-157">Dynamic service discovery.</span></span>
- <span data-ttu-id="25109-158">负载平衡。</span><span class="sxs-lookup"><span data-stu-id="25109-158">Load balancing.</span></span>
- <span data-ttu-id="25109-159">TLS 终止。</span><span class="sxs-lookup"><span data-stu-id="25109-159">TLS termination.</span></span>
- <span data-ttu-id="25109-160">HTTP 和 gRPC 代理。</span><span class="sxs-lookup"><span data-stu-id="25109-160">HTTP and gRPC proxies.</span></span>
- <span data-ttu-id="25109-161">断路器复原。</span><span class="sxs-lookup"><span data-stu-id="25109-161">Circuit breaker resiliency.</span></span>
- <span data-ttu-id="25109-162">运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="25109-162">Health checks.</span></span>
- <span data-ttu-id="25109-163">[用不](https://martinfowler.com/bliki/CanaryRelease.html)到的部署滚动更新。</span><span class="sxs-lookup"><span data-stu-id="25109-163">Rolling updates with [canary](https://martinfowler.com/bliki/CanaryRelease.html) deployments.</span></span>

<span data-ttu-id="25109-164">如前文所述，Envoy 作为挎斗部署到群集中的每个微服务。</span><span class="sxs-lookup"><span data-stu-id="25109-164">As previously discussed, Envoy is deployed as a sidecar to each microservice in the cluster.</span></span>

## <a name="integration-with-azure-kubernetes-services"></a><span data-ttu-id="25109-165">与 Azure Kubernetes 服务集成</span><span class="sxs-lookup"><span data-stu-id="25109-165">Integration with Azure Kubernetes Services</span></span>

<span data-ttu-id="25109-166">Azure 云支持 Istio，并在 Azure Kubernetes 服务中提供对该服务的直接支持。</span><span class="sxs-lookup"><span data-stu-id="25109-166">The Azure cloud embraces Istio and provides direct support for it within Azure Kubernetes Services.</span></span> <span data-ttu-id="25109-167">以下链接可帮助你入门：</span><span class="sxs-lookup"><span data-stu-id="25109-167">The following links can help you get started:</span></span>

- [<span data-ttu-id="25109-168">在 AKS 中安装 Istio</span><span class="sxs-lookup"><span data-stu-id="25109-168">Installing Istio in AKS</span></span>](https://docs.microsoft.com/azure/aks/istio-install)
- [<span data-ttu-id="25109-169">使用 AKS 和 Istio</span><span class="sxs-lookup"><span data-stu-id="25109-169">Using AKS and Istio</span></span>](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

>[!div class="step-by-step"]
><span data-ttu-id="25109-170">[上一页](infrastructure-resiliency-azure.md)
>[下一页](monitoring-health.md)</span><span class="sxs-lookup"><span data-stu-id="25109-170">[Previous](infrastructure-resiliency-azure.md)
[Next](monitoring-health.md)</span></span>
