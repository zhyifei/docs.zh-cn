---
title: "创建、 不断发展，和版本控制 microservice Api 和协定"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |创建、 不断发展，和版本控制 microservice Api 和协定"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 433711c3479eafd52bf9f5d53faf8e5707c6c624
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a><span data-ttu-id="2b296-104">创建、 不断发展，和版本控制 microservice Api 和协定</span><span class="sxs-lookup"><span data-stu-id="2b296-104">Creating, evolving, and versioning microservice APIs and contracts</span></span>

<span data-ttu-id="2b296-105">微服务 API 是服务及其客户端之间的协定。</span><span class="sxs-lookup"><span data-stu-id="2b296-105">A microservice API is a contract between the service and its clients.</span></span> <span data-ttu-id="2b296-106">你将能够独立地变化 microservice，仅当你不会中断其 API 协定，这正是协定是很重要。</span><span class="sxs-lookup"><span data-stu-id="2b296-106">You will be able to evolve a microservice independently only if you do not break its API contract, which is why the contract is so important.</span></span> <span data-ttu-id="2b296-107">如果更改协定时，它会影响客户端应用程序或 API 网关。</span><span class="sxs-lookup"><span data-stu-id="2b296-107">If you change the contract, it will impact your client applications or your API Gateway.</span></span>

<span data-ttu-id="2b296-108">API 定义的性质取决于所使用的哪个协议。</span><span class="sxs-lookup"><span data-stu-id="2b296-108">The nature of the API definition depends on which protocol you are using.</span></span> <span data-ttu-id="2b296-109">例如，如果你使用消息传送 (如[AMQP](https://www.amqp.org/))，API 包含的消息类型。</span><span class="sxs-lookup"><span data-stu-id="2b296-109">For instance, if you are using messaging (like [AMQP](https://www.amqp.org/)), the API consists of the message types.</span></span> <span data-ttu-id="2b296-110">如果你使用 HTTP 和 rest 样式服务，该 API 组成的 Url，并请求和响应的 JSON 格式。</span><span class="sxs-lookup"><span data-stu-id="2b296-110">If you are using HTTP and RESTful services, the API consists of the URLs and the request and response JSON formats.</span></span>

<span data-ttu-id="2b296-111">但是，即使你是仔细初始协定，服务 API 将需要随时间而变化。</span><span class="sxs-lookup"><span data-stu-id="2b296-111">However, even if you are thoughtful about your initial contract, a service API will need to change over time.</span></span> <span data-ttu-id="2b296-112">该事件发生时-尤其是如果你的 API 是一个由多个客户端应用程序使用的公共 API，你通常不能强制所有客户端升级到新的 API 约定。</span><span class="sxs-lookup"><span data-stu-id="2b296-112">When that happens—and especially if your API is a public API consumed by multiple client applications—you typically cannot force all clients to upgrade to your new API contract.</span></span> <span data-ttu-id="2b296-113">通常需要以增量方式部署中同时运行的服务协定的旧和新版本的方式的服务的新版本。</span><span class="sxs-lookup"><span data-stu-id="2b296-113">You usually need to incrementally deploy new versions of a service in a way that both old and new versions of a service contract are running simultaneously.</span></span> <span data-ttu-id="2b296-114">因此，务必对它的服务版本控制的策略。</span><span class="sxs-lookup"><span data-stu-id="2b296-114">Therefore, it is important to have a strategy for your service versioning.</span></span>

<span data-ttu-id="2b296-115">小型，如如果你将添加属性或参数到你的 API 的 API 更改时，使用较旧的 API 的客户端应切换，并适用于服务的新版本。</span><span class="sxs-lookup"><span data-stu-id="2b296-115">When the API changes are small, like if you add attributes or parameters to your API, clients that use an older API should switch and work with the new version of the service.</span></span> <span data-ttu-id="2b296-116">你可能能够提供默认值是必需的任何缺少的特性，并且客户端可能能够忽略任何额外的响应的属性。</span><span class="sxs-lookup"><span data-stu-id="2b296-116">You might be able to provide default values for any missing attributes that are required, and the clients might be able to ignore any extra response attributes.</span></span>

<span data-ttu-id="2b296-117">但是，有时你需要对服务 API 进行主版本号和不兼容的更改。</span><span class="sxs-lookup"><span data-stu-id="2b296-117">However, sometimes you need to make major and incompatible changes to a service API.</span></span> <span data-ttu-id="2b296-118">因为你可能不能强制客户端应用程序或服务，若要立即升级到最新版本，服务必须段支持的 api 的较旧版本。</span><span class="sxs-lookup"><span data-stu-id="2b296-118">Because you might not be able to force client applications or services to upgrade immediately to the new version, a service must support older versions of the API for some period.</span></span> <span data-ttu-id="2b296-119">如果使用不基于 HTTP 的机制例如 REST，一种方法是在 URL 中或向 HTTP 标头中嵌入的 API 版本号。</span><span class="sxs-lookup"><span data-stu-id="2b296-119">If you are using an HTTP-based mechanism such as REST, one approach is to embed the API version number in the URL or into a HTTP header.</span></span> <span data-ttu-id="2b296-120">然后你可以决定实现服务同时在同一服务实例，这两个版本，或部署每个处理 API 的版本的不同实例之间。</span><span class="sxs-lookup"><span data-stu-id="2b296-120">Then you can decide between implementing both versions of the service simultaneously within the same service instance, or deploying different instances that each handle a version of the API.</span></span> <span data-ttu-id="2b296-121">此一个好方法是[中介模式](https://en.wikipedia.org/wiki/Mediator_pattern)(例如， [MediatR 库](https://github.com/jbogard/MediatR)) 若要分离的不同实现版本到独立的处理程序。</span><span class="sxs-lookup"><span data-stu-id="2b296-121">A good approach for this is the [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern) (for example, [MediatR library](https://github.com/jbogard/MediatR)) to decouple the different implementation versions into independent handlers.</span></span>

<span data-ttu-id="2b296-122">最后，如果你使用 REST 体系结构，[超媒体](https://www.infoq.com/articles/mark-baker-hypermedia)是你的服务的版本控制的最佳解决方案，并允许 evolvable Api。</span><span class="sxs-lookup"><span data-stu-id="2b296-122">Finally, if you are using a REST architecture, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) is the best solution for versioning your services and allowing evolvable APIs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b296-123">其他资源</span><span class="sxs-lookup"><span data-stu-id="2b296-123">Additional resources</span></span>

-   <span data-ttu-id="2b296-124">**Scott Hanselman。ASP.NET 核心 RESTful Web API 版本控制变得更容易**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span><span class="sxs-lookup"><span data-stu-id="2b296-124">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
<http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span></span>

-   <span data-ttu-id="2b296-125">**版本控制 RESTful web API**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span><span class="sxs-lookup"><span data-stu-id="2b296-125">**Versioning a RESTful web API**
[*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span></span>

-   <span data-ttu-id="2b296-126">**Roy Fielding。版本控制、 超媒体和 REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning></span><span class="sxs-lookup"><span data-stu-id="2b296-126">**Roy Fielding. Versioning, Hypermedia, and REST**
<https://www.infoq.com/articles/roy-fielding-on-versioning></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2b296-127">[以前](异步-消息-基于-communication.md) [下一步] (微服务-可寻址性-服务-registry.md)</span><span class="sxs-lookup"><span data-stu-id="2b296-127">[Previous] (asynchronous-message-based-communication.md) [Next] (microservices-addressability-service-registry.md)</span></span>
