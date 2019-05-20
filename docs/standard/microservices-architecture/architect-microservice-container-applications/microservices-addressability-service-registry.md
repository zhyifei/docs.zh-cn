---
title: 微服务可寻址性和服务注册表
description: 了解容器映像注册表在微服务体系结构中的角色。
ms.date: 09/20/2018
ms.openlocfilehash: 5b601f19b60a8e989977e7135138add7644bd7b6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639972"
---
# <a name="microservices-addressability-and-the-service-registry"></a><span data-ttu-id="4c3af-103">微服务可寻址性和服务注册表</span><span class="sxs-lookup"><span data-stu-id="4c3af-103">Microservices addressability and the service registry</span></span>

<span data-ttu-id="4c3af-104">每个微服务都有一个唯一名称 (URL)，用于解析其位置。</span><span class="sxs-lookup"><span data-stu-id="4c3af-104">Each microservice has a unique name (URL) that's used to resolve its location.</span></span> <span data-ttu-id="4c3af-105">无论微服务在哪里运行，都需是可寻址的。</span><span class="sxs-lookup"><span data-stu-id="4c3af-105">Your microservice needs to be addressable wherever it's running.</span></span> <span data-ttu-id="4c3af-106">如果必须考虑哪一台计算机正在运行某个特定微服务，事情可能很快就不那么好办了。</span><span class="sxs-lookup"><span data-stu-id="4c3af-106">If you have to think about which computer is running a particular microservice, things can go bad quickly.</span></span> <span data-ttu-id="4c3af-107">按照 DNS 解析特定计算机 URL 的相同方式，微服务需要有唯一名称，以便可发现其当前位置。</span><span class="sxs-lookup"><span data-stu-id="4c3af-107">In the same way that DNS resolves a URL to a particular computer, your microservice needs to have a unique name so that its current location is discoverable.</span></span> <span data-ttu-id="4c3af-108">微服务需要可寻址的名称，使其独立于运行于其中的基础结构。</span><span class="sxs-lookup"><span data-stu-id="4c3af-108">Microservices need addressable names that make them independent from the infrastructure that they're running on.</span></span> <span data-ttu-id="4c3af-109">这意味着服务部署方式与服务发现方式之间存在交互，因为此处需要一个[服务注册表](https://microservices.io/patterns/service-registry.html)。</span><span class="sxs-lookup"><span data-stu-id="4c3af-109">This implies that there's an interaction between how your service is deployed and how it's discovered, because there needs to be a [service registry](https://microservices.io/patterns/service-registry.html).</span></span> <span data-ttu-id="4c3af-110">同样，如果计算机出现故障，注册表服务须能够指出服务的运行位置。</span><span class="sxs-lookup"><span data-stu-id="4c3af-110">In the same vein, when a computer fails, the registry service must be able to indicate where the service is now running.</span></span>

<span data-ttu-id="4c3af-111">[服务注册表模式](https://microservices.io/patterns/service-registry.html)是发现服务的一个关键部分。</span><span class="sxs-lookup"><span data-stu-id="4c3af-111">The [service registry pattern](https://microservices.io/patterns/service-registry.html) is a key part of service discovery.</span></span> <span data-ttu-id="4c3af-112">注册表是包含服务实例的网络位置的数据库。</span><span class="sxs-lookup"><span data-stu-id="4c3af-112">The registry is a database containing the network locations of service instances.</span></span> <span data-ttu-id="4c3af-113">服务注册表需保持高度可用且是最新状态。</span><span class="sxs-lookup"><span data-stu-id="4c3af-113">A service registry needs to be highly available and up-to-date.</span></span> <span data-ttu-id="4c3af-114">客户端可缓存从服务注册表获得的网络位置。</span><span class="sxs-lookup"><span data-stu-id="4c3af-114">Clients could cache network locations obtained from the service registry.</span></span> <span data-ttu-id="4c3af-115">但是，该信息最终也会过时，客户端便无法再发现服务实例。</span><span class="sxs-lookup"><span data-stu-id="4c3af-115">However, that information eventually goes out of date and clients can no longer discover service instances.</span></span> <span data-ttu-id="4c3af-116">因此，服务注册表包含了一个服务器群集，使用复制协议来维护一致性。</span><span class="sxs-lookup"><span data-stu-id="4c3af-116">Consequently, a service registry consists of a cluster of servers that use a replication protocol to maintain consistency.</span></span>

<span data-ttu-id="4c3af-117">在某些微服务部署环境中（称为集群，将在后面章节中介绍），服务发现是内置的。</span><span class="sxs-lookup"><span data-stu-id="4c3af-117">In some microservice deployment environments (called clusters, to be covered in a later section), service discovery is built-in.</span></span> <span data-ttu-id="4c3af-118">例如，具有 Kubernetes (AKS) 环境的 Azure 容器服务可以处理服务实例注册和注销。</span><span class="sxs-lookup"><span data-stu-id="4c3af-118">For example, an Azure Container Service with Kubernetes (AKS) environment can handle service instance registration and deregistration.</span></span> <span data-ttu-id="4c3af-119">它还可在每个群集主机（充当服务器端发现路由器角色）上运行一个代理。</span><span class="sxs-lookup"><span data-stu-id="4c3af-119">It also runs a proxy on each cluster host that plays the role of server-side discovery router.</span></span> <span data-ttu-id="4c3af-120">另一个示例是 Azure Service Fabric，它可通过其开箱即用的命名服务提供服务注册表。</span><span class="sxs-lookup"><span data-stu-id="4c3af-120">Another example is Azure Service Fabric, which also provides a service registry through its out-of-the-box Naming Service.</span></span>

<span data-ttu-id="4c3af-121">请注意，服务注册表和 API 网关模式之间存在一定的重叠，这也有助于解决此问题。</span><span class="sxs-lookup"><span data-stu-id="4c3af-121">Note that there's certain overlap between the service registry and the API gateway pattern, which helps solve this problem as well.</span></span> <span data-ttu-id="4c3af-122">例如，[Service Fabric 反向代理](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)是 API 网关的实现类型，该网关基于 Service Fabric 命名服务并且有助于解析内部服务的地址解析。</span><span class="sxs-lookup"><span data-stu-id="4c3af-122">For example, the [Service Fabric Reverse Proxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) is a type of implementation of an API Gateway that's based on the Service Fabric Naming Service and that helps resolve address resolution to the internal services.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4c3af-123">其他资源</span><span class="sxs-lookup"><span data-stu-id="4c3af-123">Additional resources</span></span>

- <span data-ttu-id="4c3af-124">**Chris Richardson.模式：Service Registry（服务注册表）** \\</span><span class="sxs-lookup"><span data-stu-id="4c3af-124">**Chris Richardson. Pattern: Service registry** \\</span></span>
  <https://microservices.io/patterns/service-registry.html>

- <span data-ttu-id="4c3af-125">**Auth0.The Service Registry**（服务注册表） \\</span><span class="sxs-lookup"><span data-stu-id="4c3af-125">**Auth0. The Service Registry** \\</span></span>
  <https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/>

- <span data-ttu-id="4c3af-126">**Gabriel Schenker.Service discovery**（服务发现） \\</span><span class="sxs-lookup"><span data-stu-id="4c3af-126">**Gabriel Schenker. Service discovery** \\</span></span>
  <https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/>

>[!div class="step-by-step"]
><span data-ttu-id="4c3af-127">[上一页](maintain-microservice-apis.md)
>[下一页](microservice-based-composite-ui-shape-layout.md)</span><span class="sxs-lookup"><span data-stu-id="4c3af-127">[Previous](maintain-microservice-apis.md)
[Next](microservice-based-composite-ui-shape-layout.md)</span></span>
