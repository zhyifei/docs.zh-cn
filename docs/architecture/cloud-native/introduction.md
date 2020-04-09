---
title: 云本机应用程序简介
description: 了解云原生计算
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: c9ffd34ec3deb04abddbbf85a9e5a6ed2b57c8f9
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989046"
---
# <a name="introduction-to-cloud-native-applications"></a><span data-ttu-id="bab31-103">云本机应用程序简介</span><span class="sxs-lookup"><span data-stu-id="bab31-103">Introduction to cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="bab31-104">又一天，在办公室，工作"下一件大事"。</span><span class="sxs-lookup"><span data-stu-id="bab31-104">Another day, at the office, working on "the next big thing."</span></span>

<span data-ttu-id="bab31-105">你的手机响了</span><span class="sxs-lookup"><span data-stu-id="bab31-105">Your cellphone rings.</span></span> <span data-ttu-id="bab31-106">这是你友好的招聘人员，他每天给你两次打电话询问新工作。</span><span class="sxs-lookup"><span data-stu-id="bab31-106">It's your friendly recruiter - the one who calls you twice a day about new jobs.</span></span>

<span data-ttu-id="bab31-107">但这次不同了：创业、股票和大量的资金。</span><span class="sxs-lookup"><span data-stu-id="bab31-107">But this time it's different: Start-up, equity, and plenty of funding.</span></span>

<span data-ttu-id="bab31-108">云和尖端技术的提及将您推到了边缘。</span><span class="sxs-lookup"><span data-stu-id="bab31-108">The mention of the cloud and cutting-edge technology pushes you over the edge.</span></span>

<span data-ttu-id="bab31-109">快进几个星期，你现在是设计会话的新员工，设计一个主要的电子商务应用程序。</span><span class="sxs-lookup"><span data-stu-id="bab31-109">Fast forward a few weeks and you're now a new employee in a design session architecting a major eCommerce application.</span></span> <span data-ttu-id="bab31-110">您将完成其他主要电子商务网站。</span><span class="sxs-lookup"><span data-stu-id="bab31-110">You're going to complete with other leading eCommerce sites.</span></span>

<span data-ttu-id="bab31-111">您将如何构建它？</span><span class="sxs-lookup"><span data-stu-id="bab31-111">How will you build it?</span></span>

<span data-ttu-id="bab31-112">如果您遵循过去 15 年的指导，则最有可能构建图 1.1 所示的系统。</span><span class="sxs-lookup"><span data-stu-id="bab31-112">If you follow the guidance from past 15 years, you'll most likely build the system shown in Figure 1.1.</span></span>

![传统单体设计](./media/monolithic-design.png)

<span data-ttu-id="bab31-114">**图 1-1**.</span><span class="sxs-lookup"><span data-stu-id="bab31-114">**Figure 1-1**.</span></span> <span data-ttu-id="bab31-115">传统单体设计</span><span class="sxs-lookup"><span data-stu-id="bab31-115">Traditional monolithic design</span></span>

<span data-ttu-id="bab31-116">构造包含所有域逻辑的大型核心应用程序。</span><span class="sxs-lookup"><span data-stu-id="bab31-116">You construct a large core application containing all of your domain logic.</span></span> <span data-ttu-id="bab31-117">它包括标识、目录、订购等模块。</span><span class="sxs-lookup"><span data-stu-id="bab31-117">It includes modules such as Identity, Catalog, Ordering, and more.</span></span> <span data-ttu-id="bab31-118">核心应用程序与大型关系数据库通信。</span><span class="sxs-lookup"><span data-stu-id="bab31-118">The core app communicates with a large relational database.</span></span> <span data-ttu-id="bab31-119">内核通过 HTML 界面公开功能。</span><span class="sxs-lookup"><span data-stu-id="bab31-119">The core exposes functionality via an HTML interface.</span></span>

<span data-ttu-id="bab31-120">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="bab31-120">Congratulations!</span></span>  <span data-ttu-id="bab31-121">您刚刚创建了一个整体应用程序。</span><span class="sxs-lookup"><span data-stu-id="bab31-121">You just created a monolithic application.</span></span>

<span data-ttu-id="bab31-122">不是所有都是坏的。</span><span class="sxs-lookup"><span data-stu-id="bab31-122">Not all is bad.</span></span> <span data-ttu-id="bab31-123">单体具有一些明显的优势。</span><span class="sxs-lookup"><span data-stu-id="bab31-123">Monoliths offer some distinct advantages.</span></span> <span data-ttu-id="bab31-124">例如，它们直截了当地...</span><span class="sxs-lookup"><span data-stu-id="bab31-124">For example, they're straightforward to...</span></span>

- <span data-ttu-id="bab31-125">build</span><span class="sxs-lookup"><span data-stu-id="bab31-125">build</span></span>
- <span data-ttu-id="bab31-126">测试</span><span class="sxs-lookup"><span data-stu-id="bab31-126">test</span></span>
- <span data-ttu-id="bab31-127">部署</span><span class="sxs-lookup"><span data-stu-id="bab31-127">deploy</span></span>
- <span data-ttu-id="bab31-128">解决</span><span class="sxs-lookup"><span data-stu-id="bab31-128">troubleshoot</span></span>
- <span data-ttu-id="bab31-129">scale</span><span class="sxs-lookup"><span data-stu-id="bab31-129">scale</span></span>

<span data-ttu-id="bab31-130">今天存在的许多成功应用都是作为单体创建的。</span><span class="sxs-lookup"><span data-stu-id="bab31-130">Many successful apps that exist today were created as monoliths.</span></span> <span data-ttu-id="bab31-131">该应用程序是一个热门，并继续发展，迭代后迭代，添加更多的功能。</span><span class="sxs-lookup"><span data-stu-id="bab31-131">The app is a hit and continues to evolve, iteration after iteration, adding more and more functionality.</span></span>

<span data-ttu-id="bab31-132">然而，在某些时候，你开始感到不舒服。</span><span class="sxs-lookup"><span data-stu-id="bab31-132">At some point, however, you begin to feel uncomfortable.</span></span> <span data-ttu-id="bab31-133">您发现自己失去了对应用程序的控制。</span><span class="sxs-lookup"><span data-stu-id="bab31-133">You find yourself losing control of the application.</span></span> <span data-ttu-id="bab31-134">随着时间的流逝，感觉变得更加强烈，你最终进入一种称为**恐惧循环**的状态。</span><span class="sxs-lookup"><span data-stu-id="bab31-134">As time goes on, the feeling becomes more intense and you eventually enter a state known as the **Fear Cycle**.</span></span>

- <span data-ttu-id="bab31-135">该应用程序已经变得极其复杂，没有人理解它。</span><span class="sxs-lookup"><span data-stu-id="bab31-135">The app has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="bab31-136">你害怕做出改变 - 每个改变都有意外和代价高昂的副作用。</span><span class="sxs-lookup"><span data-stu-id="bab31-136">You fear making changes - each change has unintended and costly side effects.</span></span>
- <span data-ttu-id="bab31-137">新功能/修复功能变得棘手、耗时且成本高昂。</span><span class="sxs-lookup"><span data-stu-id="bab31-137">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span>
- <span data-ttu-id="bab31-138">每个版本都尽可能小，但可能需要对整个应用程序进行全面部署。</span><span class="sxs-lookup"><span data-stu-id="bab31-138">Each release as small as it may be requires a full deployment of the entire application.</span></span>
- <span data-ttu-id="bab31-139">一个不稳定的组件可能会使整个系统崩溃。</span><span class="sxs-lookup"><span data-stu-id="bab31-139">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="bab31-140">新技术和框架不是一种选择。</span><span class="sxs-lookup"><span data-stu-id="bab31-140">New technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="bab31-141">实现敏捷交付方法是很困难的。</span><span class="sxs-lookup"><span data-stu-id="bab31-141">It's difficult to implement agile delivery methodologies.</span></span>
- <span data-ttu-id="bab31-142">随着代码库的恶化，随着无休止的"特殊情况"，体系结构侵蚀会加剧。</span><span class="sxs-lookup"><span data-stu-id="bab31-142">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="bab31-143">顾问们叫你重写它。</span><span class="sxs-lookup"><span data-stu-id="bab31-143">The consultants tell you to rewrite it.</span></span>

<span data-ttu-id="bab31-144">许多组织通过采用云原生方法来构建系统来解决整体恐惧循环。</span><span class="sxs-lookup"><span data-stu-id="bab31-144">Many organizations have addressed the monolithic fear cycle by adopting a cloud-native approach to building systems.</span></span> <span data-ttu-id="bab31-145">图 1-2 显示了应用云本机技术和实践构建的相同系统。</span><span class="sxs-lookup"><span data-stu-id="bab31-145">Figure 1-2 shows the same system built applying cloud-native techniques and practices.</span></span>

![云原生设计](./media/cloud-native-design.png)

<span data-ttu-id="bab31-147">**图1-2**.</span><span class="sxs-lookup"><span data-stu-id="bab31-147">**Figure 1-2**.</span></span> <span data-ttu-id="bab31-148">云原生设计</span><span class="sxs-lookup"><span data-stu-id="bab31-148">Cloud-native design</span></span>

<span data-ttu-id="bab31-149">请注意如何在一组小型孤立的微服务中分解应用程序。</span><span class="sxs-lookup"><span data-stu-id="bab31-149">Note how the application is decomposed across a set of small isolated microservices.</span></span> <span data-ttu-id="bab31-150">每个服务都是自包含的，并封装自己的代码、数据和依赖项。</span><span class="sxs-lookup"><span data-stu-id="bab31-150">Each service is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="bab31-151">每个组件都部署在软件容器中，并由容器协调器管理。</span><span class="sxs-lookup"><span data-stu-id="bab31-151">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="bab31-152">每个服务都拥有自己的数据存储，而不是大型关系数据库，其类型因数据需求而异。</span><span class="sxs-lookup"><span data-stu-id="bab31-152">Instead of a large relational database, each service owns it own datastore, the type of which vary based upon the data needs.</span></span> <span data-ttu-id="bab31-153">请注意某些服务如何依赖于关系数据库，但在 NoSQL 数据库上依赖于其他服务。</span><span class="sxs-lookup"><span data-stu-id="bab31-153">Note how some services depend on a relational database, but other on NoSQL databases.</span></span> <span data-ttu-id="bab31-154">一个服务将其状态存储在分布式缓存中。</span><span class="sxs-lookup"><span data-stu-id="bab31-154">One service stores its state in a distributed cache.</span></span> <span data-ttu-id="bab31-155">请注意，所有流量如何通过 API 网关服务路由，该服务负责将流量路由到核心后端服务并强制实施许多交叉问题。</span><span class="sxs-lookup"><span data-stu-id="bab31-155">Note how all traffic routes through an API Gateway service that is responsible for routing traffic to the core back-end services  and enforcing many cross-cutting concerns.</span></span> <span data-ttu-id="bab31-156">最重要的是，该应用程序充分利用了现代云平台中的可扩展性和弹性功能。</span><span class="sxs-lookup"><span data-stu-id="bab31-156">Most importantly, the application takes full advantage of the scalability and resiliency features found in modern cloud platforms.</span></span>

### <a name="cloud-native-computing"></a><span data-ttu-id="bab31-157">云原生计算</span><span class="sxs-lookup"><span data-stu-id="bab31-157">Cloud-native computing</span></span>

<span data-ttu-id="bab31-158">嗯。。。我们只是使用了"*云原生*"这个词。</span><span class="sxs-lookup"><span data-stu-id="bab31-158">Hmm... We just used the term, "*Cloud Native*."</span></span> <span data-ttu-id="bab31-159">你首先想到的可能是，"这到底是什么意思？</span><span class="sxs-lookup"><span data-stu-id="bab31-159">You first thought might be, "What exactly does that mean?"</span></span> <span data-ttu-id="bab31-160">另一个行业流行语由软件供应商捏造，以销售更多的东西？</span><span class="sxs-lookup"><span data-stu-id="bab31-160">Another industry buzzword concocted by software vendors to market more stuff?"</span></span>

<span data-ttu-id="bab31-161">幸运的是，这是完全不同的，希望这本书将有助于说服你。</span><span class="sxs-lookup"><span data-stu-id="bab31-161">Fortunately it's far different and hopefully this book will help convince you.</span></span>

<span data-ttu-id="bab31-162">在短时间内，云原生已成为软件行业的驱动力。</span><span class="sxs-lookup"><span data-stu-id="bab31-162">Within a short time, cloud native has become a driving trend in the software industry.</span></span> <span data-ttu-id="bab31-163">这是一种构建大型复杂系统的新方法，该方法充分利用了现代软件开发实践、技术和云基础架构。</span><span class="sxs-lookup"><span data-stu-id="bab31-163">It's a new way to think about building large, complex systems, an approach that takes full advantage of modern software development practices, technologies, and cloud infrastructure.</span></span> <span data-ttu-id="bab31-164">该方法改变了您设计、实施、部署和操作系统的方式。</span><span class="sxs-lookup"><span data-stu-id="bab31-164">The approach changes the way you design, implement, deploy, and operationalize systems.</span></span>

<span data-ttu-id="bab31-165">与推动我们行业的持续炒作不同，云原生是"*真实*"。"。</span><span class="sxs-lookup"><span data-stu-id="bab31-165">Unlike the continuous hype that drives our industry, cloud native is "*for-real*".</span></span> <span data-ttu-id="bab31-166">以[云原生计算基金会](https://www.cncf.io/)（CNCF） 为例，该基金会由 300 多家大公司组成，其章程使云原生计算在技术和云堆栈中无处不在。</span><span class="sxs-lookup"><span data-stu-id="bab31-166">Consider the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), a consortium of over 300 major corporations with a charter to make cloud-native computing ubiquitous across technology and cloud stacks.</span></span> <span data-ttu-id="bab31-167">作为最具影响力的开源集团之一，它承载着 GitHub 中许多增长最快的开源项目。</span><span class="sxs-lookup"><span data-stu-id="bab31-167">As one of the most influential open-source groups, it hosts many of the fastest-growing open source-projects in GitHub.</span></span> <span data-ttu-id="bab31-168">这些项目包括[库伯内斯](https://kubernetes.io/)、[普罗米特斯](https://prometheus.io/)、[赫尔姆](https://helm.sh/)、[特使](https://www.envoyproxy.io/)和[gRPC](https://grpc.io/)等。</span><span class="sxs-lookup"><span data-stu-id="bab31-168">They include projects such as [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/), and [gRPC](https://grpc.io/).</span></span>

<span data-ttu-id="bab31-169">CNCF 培育了开源和供应商中立的生态系统。</span><span class="sxs-lookup"><span data-stu-id="bab31-169">The CNCF fosters an ecosystem of open-source and vendor-neutrality.</span></span> <span data-ttu-id="bab31-170">遵循该领导，我们提出了与技术无关的云原生原则、模式和最佳实践。</span><span class="sxs-lookup"><span data-stu-id="bab31-170">Following that lead, we present cloud-native principles, patterns, and best practices that are technology agnostic.</span></span> <span data-ttu-id="bab31-171">同时，我们讨论 Microsoft Azure 云中用于构建云本机系统的服务和基础结构。</span><span class="sxs-lookup"><span data-stu-id="bab31-171">At the same time, we discuss the services and infrastructure available in the Microsoft Azure cloud for constructing cloud-native systems.</span></span>

<span data-ttu-id="bab31-172">那么，什么是云原生？</span><span class="sxs-lookup"><span data-stu-id="bab31-172">So, what exactly is Cloud Native?</span></span> <span data-ttu-id="bab31-173">坐下来，放松，让我们帮助您探索这个新世界。</span><span class="sxs-lookup"><span data-stu-id="bab31-173">Sit back, relax, and let us help you explore this new world.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bab31-174">[上一页](index.md)
>[下一页](definition.md)</span><span class="sxs-lookup"><span data-stu-id="bab31-174">[Previous](index.md)
[Next](definition.md)</span></span>
