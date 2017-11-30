---
title: "微服务可寻址性和服务注册表"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |微服务可寻址性和服务注册表"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 19a0200dadfb90a455de690d880f4eeae4772ed7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-addressability-and-the-service-registry"></a><span data-ttu-id="28621-104">微服务可寻址性和服务注册表</span><span class="sxs-lookup"><span data-stu-id="28621-104">Microservices addressability and the service registry</span></span>

<span data-ttu-id="28621-105">每个微服务具有一个唯一名称 (URL)，用于解析其位置。</span><span class="sxs-lookup"><span data-stu-id="28621-105">Each microservice has a unique name (URL) that is used to resolve its location.</span></span> <span data-ttu-id="28621-106">你微服务必须是可寻址的只要它正在运行。</span><span class="sxs-lookup"><span data-stu-id="28621-106">Your microservice needs to be addressable wherever it is running.</span></span> <span data-ttu-id="28621-107">如果必须考虑有关哪台计算机正在运行特定的微服务，操作可能会快速错误。</span><span class="sxs-lookup"><span data-stu-id="28621-107">If you have to think about which computer is running a particular microservice, things can go bad quickly.</span></span> <span data-ttu-id="28621-108">在 DNS 解析 URL，到特定计算机的方式相同，你的 microservice 需要具有唯一的名称，以便其当前的位置是可发现。</span><span class="sxs-lookup"><span data-stu-id="28621-108">In the same way that DNS resolves a URL to a particular computer, your microservice needs to have a unique name so that its current location is discoverable.</span></span> <span data-ttu-id="28621-109">微服务需要可寻址使它们独立于在运行的基础结构的名称。</span><span class="sxs-lookup"><span data-stu-id="28621-109">Microservices need addressable names that make them independent from the infrastructure that they are running on.</span></span> <span data-ttu-id="28621-110">这意味着由于需要有没有你的服务的部署方式与它如何发现之间交互[服务注册表](http://microservices.io/patterns/service-registry.html)。</span><span class="sxs-lookup"><span data-stu-id="28621-110">This implies that there is an interaction between how your service is deployed and how it is discovered, because there needs to be a [service registry](http://microservices.io/patterns/service-registry.html).</span></span> <span data-ttu-id="28621-111">在相同情况下，计算机发生故障，注册表服务必须能够指示该服务现在运行。</span><span class="sxs-lookup"><span data-stu-id="28621-111">In the same vein, when a computer fails, the registry service must be able to indicate where the service is now running.</span></span>

<span data-ttu-id="28621-112">[服务注册表模式](http://microservices.io/patterns/service-registry.html)是服务发现的一个关键部分。</span><span class="sxs-lookup"><span data-stu-id="28621-112">The [service registry pattern](http://microservices.io/patterns/service-registry.html) is a key part of service discovery.</span></span> <span data-ttu-id="28621-113">注册表是包含服务实例的网络位置的数据库。</span><span class="sxs-lookup"><span data-stu-id="28621-113">The registry is a database containing the network locations of service instances.</span></span> <span data-ttu-id="28621-114">服务注册表需要高可用性和最新。</span><span class="sxs-lookup"><span data-stu-id="28621-114">A service registry needs to be highly available and up to date.</span></span> <span data-ttu-id="28621-115">客户端无法缓存从服务注册表中获得的网络位置。</span><span class="sxs-lookup"><span data-stu-id="28621-115">Clients could cache network locations obtained from the service registry.</span></span> <span data-ttu-id="28621-116">但是，该信息最终将过期并且客户端不再可发现服务实例。</span><span class="sxs-lookup"><span data-stu-id="28621-116">However, that information eventually goes out of date and clients can no longer discover service instances.</span></span> <span data-ttu-id="28621-117">因此，服务注册表包含使用复制协议来保持一致性的服务器的群集。</span><span class="sxs-lookup"><span data-stu-id="28621-117">Consequently, a service registry consists of a cluster of servers that use a replication protocol to maintain consistency.</span></span>

<span data-ttu-id="28621-118">在某些微服务部署环境中 （称为群集，若要在更高版本的部分讨论），服务发现是内置的。</span><span class="sxs-lookup"><span data-stu-id="28621-118">In some microservice deployment environments (called clusters, to be covered in a later section), service discovery is built-in.</span></span> <span data-ttu-id="28621-119">例如，在一个 Azure 容器服务的环境 Kubernetes DC/操作系统 Marathon 可以处理服务实例注册和取消注册。</span><span class="sxs-lookup"><span data-stu-id="28621-119">For example, within an Azure Container Service environment, Kubernetes and DC/OS with Marathon can handle service instance registration and deregistration.</span></span> <span data-ttu-id="28621-120">它们还充当的角色的服务器端发现路由器每个群集主机上运行代理。</span><span class="sxs-lookup"><span data-stu-id="28621-120">They also run a proxy on each cluster host that plays the role of server-side discovery router.</span></span> <span data-ttu-id="28621-121">另一个示例是 Azure Service Fabric，还提供了通过其中的框命名服务的服务注册表。</span><span class="sxs-lookup"><span data-stu-id="28621-121">Another example is Azure Service Fabric, which also provides a service registry through its out-of-the-box Naming Service.</span></span>

<span data-ttu-id="28621-122">请注意，某些服务注册表和 API 的网关模式，这有助于解决此问题也之间的重叠。</span><span class="sxs-lookup"><span data-stu-id="28621-122">Note that there is certain overlap between the service registry and the API gateway pattern, which helps solve this problem as well.</span></span> <span data-ttu-id="28621-123">例如，[服务 Fabric 反向代理](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)是一种基于服务 Fabrice 命名服务，以帮助解决地址解析到内部服务的 API 网关的实现。</span><span class="sxs-lookup"><span data-stu-id="28621-123">For example, the [Service Fabric Reverse Proxy](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) is a type of implementation of an API Gateway that is based on the Service Fabrice Naming Service and that helps resolve address resolution to the internal services.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28621-124">其他资源</span><span class="sxs-lookup"><span data-stu-id="28621-124">Additional resources</span></span>

-   <span data-ttu-id="28621-125">**Chris Richardson。模式： 服务注册表**
    *http://microservices.io/patterns/service-registry.html*</span><span class="sxs-lookup"><span data-stu-id="28621-125">**Chris Richardson. Pattern: Service registry**
*http://microservices.io/patterns/service-registry.html*</span></span>

-   <span data-ttu-id="28621-126">**Auth0。服务注册表**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)</span><span class="sxs-lookup"><span data-stu-id="28621-126">**Auth0. The Service Registry**
[*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)</span></span>

-   <span data-ttu-id="28621-127">**Gabriel Schenker。服务发现**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)</span><span class="sxs-lookup"><span data-stu-id="28621-127">**Gabriel Schenker. Service discovery**
[*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="28621-128">[以前](维护-microservice-apis.md) [下一步] (microservice-based-composite-ui-shape-layout.md)</span><span class="sxs-lookup"><span data-stu-id="28621-128">[Previous] (maintain-microservice-apis.md) [Next] (microservice-based-composite-ui-shape-layout.md)</span></span>
