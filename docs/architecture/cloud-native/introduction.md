---
title: 云本机应用程序简介
description: 了解云本机计算
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: 1d3679c7f1ab940d7ab3e194c200483b63276883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841767"
---
# <a name="introduction-to-cloud-native-applications"></a><span data-ttu-id="ac76b-103">云本机应用程序简介</span><span class="sxs-lookup"><span data-stu-id="ac76b-103">Introduction to cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ac76b-104">另一天，在办公室，处理 "下一项重大事情"。</span><span class="sxs-lookup"><span data-stu-id="ac76b-104">Another day, at the office, working on "the next big thing."</span></span>

<span data-ttu-id="ac76b-105">你的手机环。</span><span class="sxs-lookup"><span data-stu-id="ac76b-105">Your cellphone rings.</span></span> <span data-ttu-id="ac76b-106">这是你的友好招聘人员，一天向你致电两次新作业。</span><span class="sxs-lookup"><span data-stu-id="ac76b-106">It's your friendly recruiter - the one who calls you twice a day about new jobs.</span></span>

<span data-ttu-id="ac76b-107">但这种情况不同：启动、权益和大量投资。</span><span class="sxs-lookup"><span data-stu-id="ac76b-107">But this time it's different: Start-up, equity, and plenty of funding.</span></span>

<span data-ttu-id="ac76b-108">提到的云和先进的技术将会推动你的边缘。</span><span class="sxs-lookup"><span data-stu-id="ac76b-108">The mention of the cloud and cutting-edge technology pushes you over the edge.</span></span>

<span data-ttu-id="ac76b-109">快几周后，你现在就可以在设计会话中构建一个新的员工来构建主要的电子商务应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac76b-109">Fast forward a few weeks and you're now a new employee in a design session architecting a major eCommerce application.</span></span> <span data-ttu-id="ac76b-110">你将在其他领先的电子商务网站上完成。</span><span class="sxs-lookup"><span data-stu-id="ac76b-110">You're going to complete with other leading eCommerce sites.</span></span>

<span data-ttu-id="ac76b-111">您将如何生成它？</span><span class="sxs-lookup"><span data-stu-id="ac76b-111">How will you build it?</span></span>

<span data-ttu-id="ac76b-112">如果按照过去15年的指导进行操作，则很可能会生成图1.1 所示的系统。</span><span class="sxs-lookup"><span data-stu-id="ac76b-112">If you follow the guidance from past 15 years, you'll most likely build the system shown in Figure 1.1.</span></span>

![传统的整体设计](./media/monolithic-design.png)

<span data-ttu-id="ac76b-114">**图 1-1**。</span><span class="sxs-lookup"><span data-stu-id="ac76b-114">**Figure 1-1**.</span></span> <span data-ttu-id="ac76b-115">传统的整体设计</span><span class="sxs-lookup"><span data-stu-id="ac76b-115">Traditional monolithic design</span></span>

<span data-ttu-id="ac76b-116">构造包含所有域逻辑的大型核心应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac76b-116">You construct a large core application containing all of your domain logic.</span></span> <span data-ttu-id="ac76b-117">它包括标识、目录、排序等模块。</span><span class="sxs-lookup"><span data-stu-id="ac76b-117">It includes modules such as Identity, Catalog, Ordering, and more.</span></span> <span data-ttu-id="ac76b-118">核心应用与大型关系数据库通信。</span><span class="sxs-lookup"><span data-stu-id="ac76b-118">The core app communicates with a large relational database.</span></span> <span data-ttu-id="ac76b-119">核心通过 HTML 接口公开功能。</span><span class="sxs-lookup"><span data-stu-id="ac76b-119">The core exposes functionality via an HTML interface.</span></span>

<span data-ttu-id="ac76b-120">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="ac76b-120">Congratulations!</span></span>  <span data-ttu-id="ac76b-121">刚刚创建了一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac76b-121">You just created a monolithic application.</span></span>

<span data-ttu-id="ac76b-122">并非全部都是正确的。</span><span class="sxs-lookup"><span data-stu-id="ac76b-122">Not all is bad.</span></span> <span data-ttu-id="ac76b-123">固化结构提供了一些独特的优势。</span><span class="sxs-lookup"><span data-stu-id="ac76b-123">Monoliths offer some distinct advantages.</span></span> <span data-ttu-id="ac76b-124">例如，它们是非常简单的 。</span><span class="sxs-lookup"><span data-stu-id="ac76b-124">For example, they're straightforward to...</span></span>

- <span data-ttu-id="ac76b-125">生成</span><span class="sxs-lookup"><span data-stu-id="ac76b-125">build</span></span>
- <span data-ttu-id="ac76b-126">测试</span><span class="sxs-lookup"><span data-stu-id="ac76b-126">test</span></span>
- <span data-ttu-id="ac76b-127">满怀信心</span><span class="sxs-lookup"><span data-stu-id="ac76b-127">deploy</span></span>
- <span data-ttu-id="ac76b-128">相关</span><span class="sxs-lookup"><span data-stu-id="ac76b-128">troubleshoot</span></span>
- <span data-ttu-id="ac76b-129">小数位数</span><span class="sxs-lookup"><span data-stu-id="ac76b-129">scale</span></span>

<span data-ttu-id="ac76b-130">目前存在的许多成功应用都创建为固化结构。</span><span class="sxs-lookup"><span data-stu-id="ac76b-130">Many successful apps that exist today were created as monoliths.</span></span> <span data-ttu-id="ac76b-131">该应用程序是点击的，在迭代后将继续发展，增加了更多的功能。</span><span class="sxs-lookup"><span data-stu-id="ac76b-131">The app is a hit and continues to evolve, iteration after iteration, adding more and more functionality.</span></span>

<span data-ttu-id="ac76b-132">但在某些时候，你会感到不安。</span><span class="sxs-lookup"><span data-stu-id="ac76b-132">At some point, however, you begin to feel uncomfortable.</span></span> <span data-ttu-id="ac76b-133">你发现自己失去了对应用程序的控制。</span><span class="sxs-lookup"><span data-stu-id="ac76b-133">You find yourself losing control of the application.</span></span> <span data-ttu-id="ac76b-134">随着时间的推出，感觉就变得越来越多，最终**进入了所谓的状态。**</span><span class="sxs-lookup"><span data-stu-id="ac76b-134">As time goes on, the feeling becomes more intense and you eventually enter a state known as the **Fear Cycle**.</span></span>

- <span data-ttu-id="ac76b-135">此应用已变得充分，因此不会有任何人理解它。</span><span class="sxs-lookup"><span data-stu-id="ac76b-135">The app has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="ac76b-136">您担心进行更改-每个更改都有意想不到和昂贵的副作用。</span><span class="sxs-lookup"><span data-stu-id="ac76b-136">You fear making changes - each change has unintended and costly side effects.</span></span>
- <span data-ttu-id="ac76b-137">新功能/修补变得更加棘手、耗时且成本高昂。</span><span class="sxs-lookup"><span data-stu-id="ac76b-137">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span>
- <span data-ttu-id="ac76b-138">每个版本都很小，因为它可能需要整个应用程序的完整部署。</span><span class="sxs-lookup"><span data-stu-id="ac76b-138">Each release as small as it may be requires a full deployment of the entire application.</span></span>
- <span data-ttu-id="ac76b-139">一个不稳定的组件可能会损坏整个系统。</span><span class="sxs-lookup"><span data-stu-id="ac76b-139">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="ac76b-140">不能选择新的技术和框架。</span><span class="sxs-lookup"><span data-stu-id="ac76b-140">New technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="ac76b-141">很难实现敏捷交付方法。</span><span class="sxs-lookup"><span data-stu-id="ac76b-141">It's difficult to implement agile delivery methodologies.</span></span>
- <span data-ttu-id="ac76b-142">体系结构 erosion 在中将设置为代码库 deteriorates，其中包含永不结束的 "特殊情况"。</span><span class="sxs-lookup"><span data-stu-id="ac76b-142">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="ac76b-143">顾问会告诉你重写它。</span><span class="sxs-lookup"><span data-stu-id="ac76b-143">The consultants tell you to rewrite it.</span></span>

<span data-ttu-id="ac76b-144">许多组织都采用了一种用于构建系统的云本机方法来解决了单一的恐惧。</span><span class="sxs-lookup"><span data-stu-id="ac76b-144">Many organizations have addressed the monolithic fear cycle by adopting a cloud-native approach to building systems.</span></span> <span data-ttu-id="ac76b-145">图1-2 显示了一种在应用程序本机技术和实践的同时构建的系统。</span><span class="sxs-lookup"><span data-stu-id="ac76b-145">Figure 1-2 shows the same system built applying cloud-native techniques and practices.</span></span>

![云-本机设计](./media/cloud-native-design.png)

<span data-ttu-id="ac76b-147">**图 1-2**。</span><span class="sxs-lookup"><span data-stu-id="ac76b-147">**Figure 1-2**.</span></span> <span data-ttu-id="ac76b-148">云-本机设计</span><span class="sxs-lookup"><span data-stu-id="ac76b-148">Cloud-native design</span></span>

<span data-ttu-id="ac76b-149">请注意应用程序如何在一组小型独立微服务中分解。</span><span class="sxs-lookup"><span data-stu-id="ac76b-149">Note how the application is decomposed across a set of small isolated microservices.</span></span> <span data-ttu-id="ac76b-150">每个服务都是自包含的，它封装自己的代码、数据和依赖项。</span><span class="sxs-lookup"><span data-stu-id="ac76b-150">Each service is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="ac76b-151">每个部署在软件容器中并由容器 orchestrator 管理。</span><span class="sxs-lookup"><span data-stu-id="ac76b-151">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="ac76b-152">每个服务都拥有其自己的数据存储，而不是大型关系数据库，而这种数据库的类型根据数据需求而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ac76b-152">Instead of a large relational database, each service owns it own datastore, the type of which vary based upon the data needs.</span></span> <span data-ttu-id="ac76b-153">请注意某些服务如何依赖于关系数据库，但其他服务依赖于 NoSQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="ac76b-153">Note how some services depend on a relational database, but other on NoSQL databases.</span></span> <span data-ttu-id="ac76b-154">一个服务将其状态存储在分布式缓存中。</span><span class="sxs-lookup"><span data-stu-id="ac76b-154">One service stores its state in a distributed cache.</span></span> <span data-ttu-id="ac76b-155">请注意所有流量如何通过 API 网关服务进行路由，该服务负责将流量路由到核心后端服务，并强制执行许多交叉切削问题。</span><span class="sxs-lookup"><span data-stu-id="ac76b-155">Note how all traffic routes through an API Gateway service that is responsible for routing traffic to the core back-end services  and enforcing many cross-cutting concerns.</span></span> <span data-ttu-id="ac76b-156">最重要的是，应用程序充分利用了新式云平台中的可伸缩性和复原功能。</span><span class="sxs-lookup"><span data-stu-id="ac76b-156">Most importantly, the application takes full advantage of the scalability and resiliency features found in modern cloud platforms.</span></span>

### <a name="cloud-native-computing"></a><span data-ttu-id="ac76b-157">云本机计算</span><span class="sxs-lookup"><span data-stu-id="ac76b-157">Cloud-native computing</span></span>

<span data-ttu-id="ac76b-158">嗯 。我们刚才使用了 "*云本机*" 这一术语。</span><span class="sxs-lookup"><span data-stu-id="ac76b-158">Hmm... We just used the term, "*Cloud Native*."</span></span> <span data-ttu-id="ac76b-159">首先，您可能会说 "这是什么意思呢？"</span><span class="sxs-lookup"><span data-stu-id="ac76b-159">You first thought might be, “What exactly does that mean?”</span></span> <span data-ttu-id="ac76b-160">软件供应商 concocted 的另一个行业流行用语？</span><span class="sxs-lookup"><span data-stu-id="ac76b-160">Another industry buzzword concocted by software vendors to market more stuff?”</span></span>

<span data-ttu-id="ac76b-161">幸运的是，这种方法并不是很容易的，因此，这本书有助于说服你。</span><span class="sxs-lookup"><span data-stu-id="ac76b-161">Fortunately it’s far different and hopefully this book will help convince you.</span></span>

<span data-ttu-id="ac76b-162">在短期内，云本机已成为软件行业中的推动趋势。</span><span class="sxs-lookup"><span data-stu-id="ac76b-162">Within a short time, cloud native has become a driving trend in the software industry.</span></span> <span data-ttu-id="ac76b-163">这是一种新的方法，可用于构建大型复杂系统，这是一种充分利用新式软件开发做法、技术和云基础结构的方法。</span><span class="sxs-lookup"><span data-stu-id="ac76b-163">It’s a new way to think about building large, complex systems, an approach that takes full advantage of modern software development practices, technologies, and cloud infrastructure.</span></span> <span data-ttu-id="ac76b-164">此方法会改变您设计、实施、部署和操作系统的方式。</span><span class="sxs-lookup"><span data-stu-id="ac76b-164">The approach changes the way you design, implement, deploy, and operationalize systems.</span></span>

<span data-ttu-id="ac76b-165">与推动我们的行业的连续夸大宣传不同，云本机是 "*真实*的"。</span><span class="sxs-lookup"><span data-stu-id="ac76b-165">Unlike the continuous hype that drives our industry, cloud native is “*for-real*.”</span></span> <span data-ttu-id="ac76b-166">请考虑[云本机计算基础](https://www.cncf.io/)（CNCF），这是一位超过300的主要企业，旨在使云本机计算跨技术和云堆栈。</span><span class="sxs-lookup"><span data-stu-id="ac76b-166">Consider the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), a consortium of over 300 major corporations with a charter to make cloud-native computing ubiquitous across technology and cloud stacks.</span></span> <span data-ttu-id="ac76b-167">作为最具影响力的开源组之一，它在 GitHub 中托管了许多增长最快的开放源代码项目。</span><span class="sxs-lookup"><span data-stu-id="ac76b-167">As one of the most influential open-source groups, it hosts many of the fastest-growing open source-projects in GitHub.</span></span> <span data-ttu-id="ac76b-168">其中包括[Kubernetes](https://kubernetes.io/)、 [Prometheus](https://prometheus.io/)、 [Helm](https://helm.sh/)、 [Envoy](https://www.envoyproxy.io/)和[gRPC](https://grpc.io/)等项目。</span><span class="sxs-lookup"><span data-stu-id="ac76b-168">They include projects such as [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/), and [gRPC](https://grpc.io/).</span></span>

<span data-ttu-id="ac76b-169">CNCF 促进开源和供应商中立的生态系统。</span><span class="sxs-lookup"><span data-stu-id="ac76b-169">The CNCF fosters an ecosystem of open-source and vendor-neutrality.</span></span> <span data-ttu-id="ac76b-170">接下来，我们提供了云本机原则、模式和最佳做法，它们与技术无关。</span><span class="sxs-lookup"><span data-stu-id="ac76b-170">Following that lead, we present cloud-native principles, patterns, and best practices that are technology agnostic.</span></span> <span data-ttu-id="ac76b-171">同时，我们讨论 Microsoft Azure 云中提供的服务和基础结构，用于构造云本机系统。</span><span class="sxs-lookup"><span data-stu-id="ac76b-171">At the same time, we discuss the services and infrastructure available in the Microsoft Azure cloud for constructing cloud-native systems.</span></span>

<span data-ttu-id="ac76b-172">那么，云的确切情况如何呢？</span><span class="sxs-lookup"><span data-stu-id="ac76b-172">So, what exactly is Cloud Native?</span></span> <span data-ttu-id="ac76b-173">让我们来帮助您探索这一新的世界。</span><span class="sxs-lookup"><span data-stu-id="ac76b-173">Sit back, relax, and let us help you explore this new world.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ac76b-174">[上一页](index.md)
>[下一页](definition.md)</span><span class="sxs-lookup"><span data-stu-id="ac76b-174">[Previous](index.md)
[Next](definition.md)</span></span>
