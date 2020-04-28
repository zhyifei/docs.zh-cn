---
title: 利用容器和协调器
description: 利用 Azure 中的 Docker 容器和 Kubernetes 协调器
ms.date: 04/13/2020
ms.openlocfilehash: 3d94433250f02a8df2c27ebc89a101e1e8d15030
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199828"
---
# <a name="leveraging-containers-and-orchestrators"></a><span data-ttu-id="50fff-103">利用容器和协调器</span><span class="sxs-lookup"><span data-stu-id="50fff-103">Leveraging containers and orchestrators</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="50fff-104">容器和协调器旨在解决单一部署方法常见的问题。</span><span class="sxs-lookup"><span data-stu-id="50fff-104">Containers and orchestrators are designed to solve problems common to monolithic deployment approaches.</span></span>

## <a name="challenges-with-monolithic-deployments"></a><span data-ttu-id="50fff-105">单一部署难题</span><span class="sxs-lookup"><span data-stu-id="50fff-105">Challenges with monolithic deployments</span></span>

<span data-ttu-id="50fff-106">传统上，大多数应用程序都部署为单个单元。</span><span class="sxs-lookup"><span data-stu-id="50fff-106">Traditionally, most applications have been deployed as a single unit.</span></span> <span data-ttu-id="50fff-107">此类应用程序称为单体架构。</span><span class="sxs-lookup"><span data-stu-id="50fff-107">Such applications are referred to as a monolith.</span></span> <span data-ttu-id="50fff-108">这种将应用程序作为单一单元进行部署的通用方法，即使它们由多个模块或程序集组成，也称为单片体系结构，如图3-1 所示。</span><span class="sxs-lookup"><span data-stu-id="50fff-108">This general approach of deploying applications as single units even if they're composed of multiple modules or assemblies is known as monolithic architecture, as shown in Figure 3-1.</span></span>

![整体体系结构。](./media/monolithic-architecture.png)

<span data-ttu-id="50fff-110">**图 3-1**。</span><span class="sxs-lookup"><span data-stu-id="50fff-110">**Figure 3-1**.</span></span> <span data-ttu-id="50fff-111">整体体系结构。</span><span class="sxs-lookup"><span data-stu-id="50fff-111">Monolithic architecture.</span></span>

<span data-ttu-id="50fff-112">尽管它们具有简易性的优点，但单一体系结构面临着许多挑战：</span><span class="sxs-lookup"><span data-stu-id="50fff-112">Although they have the benefit of simplicity, monolithic architectures face a number of challenges:</span></span>

### <a name="deployment"></a><span data-ttu-id="50fff-113">部署</span><span class="sxs-lookup"><span data-stu-id="50fff-113">Deployment</span></span>

<span data-ttu-id="50fff-114">即使只进行了少量更改，单一应用程序也需要完整的整个应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="50fff-114">Monolithic applications require a full deployment of the entire application, even if only a small change has been made.</span></span> <span data-ttu-id="50fff-115">完全部署可能成本高昂，并且容易出错。</span><span class="sxs-lookup"><span data-stu-id="50fff-115">Full deployments can be expensive and error prone.</span></span> <span data-ttu-id="50fff-116">此外，他们还需要重新启动应用程序，这会暂时影响不可用。</span><span class="sxs-lookup"><span data-stu-id="50fff-116">Additionally, they require a restart of the application, which temporarily impacts unavailability.</span></span>

### <a name="scaling"></a><span data-ttu-id="50fff-117">扩展</span><span class="sxs-lookup"><span data-stu-id="50fff-117">Scaling</span></span>

<span data-ttu-id="50fff-118">整体应用程序完全承载于单个计算机实例上，通常需要高容量的硬件。</span><span class="sxs-lookup"><span data-stu-id="50fff-118">A monolithic application is hosted entirely on a single machine instance, often requiring high-capability hardware.</span></span> <span data-ttu-id="50fff-119">如果单体架构的任何部分需要缩放，则必须将整个应用程序的另一个副本部署到另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="50fff-119">If any part of the monolith requires scaling, another copy of the entire application must be deployed to another machine.</span></span> <span data-ttu-id="50fff-120">使用单体架构时，不能单独缩放应用程序组件-它是全部或无。</span><span class="sxs-lookup"><span data-stu-id="50fff-120">With a monolith, you can't scale application components individually - it's all or nothing.</span></span> <span data-ttu-id="50fff-121">缩放不需要缩放的组件会导致资源利用率低下且成本高昂。</span><span class="sxs-lookup"><span data-stu-id="50fff-121">Scaling components that don't require scaling results in inefficient and costly resource usage.</span></span>

### <a name="environment"></a><span data-ttu-id="50fff-122">环境</span><span class="sxs-lookup"><span data-stu-id="50fff-122">Environment</span></span>

<span data-ttu-id="50fff-123">整体应用程序通常部署到具有预安装的操作系统、运行时和库依赖项的宿主环境。</span><span class="sxs-lookup"><span data-stu-id="50fff-123">Monolithic applications are typically deployed to a hosting environment with a pre-installed operating system, runtime, and library dependencies.</span></span> <span data-ttu-id="50fff-124">此环境可能与开发或测试应用程序的环境不匹配。</span><span class="sxs-lookup"><span data-stu-id="50fff-124">This environment may not match that upon which the application was developed or tested.</span></span> <span data-ttu-id="50fff-125">应用程序环境之间的不一致性是单一部署问题的常见根源。</span><span class="sxs-lookup"><span data-stu-id="50fff-125">Inconsistencies across application environments are a common source of problems for monolithic deployments.</span></span>

### <a name="coupling"></a><span data-ttu-id="50fff-126">耦合</span><span class="sxs-lookup"><span data-stu-id="50fff-126">Coupling</span></span>

<span data-ttu-id="50fff-127">单一应用程序可能会在其功能组件间经历较高的耦合。</span><span class="sxs-lookup"><span data-stu-id="50fff-127">A monolithic application is likely to experience high coupling across its functional components.</span></span> <span data-ttu-id="50fff-128">如果没有硬边界，系统更改通常会产生意外的、代价高昂的副作用。</span><span class="sxs-lookup"><span data-stu-id="50fff-128">Without hard boundaries, system changes often result in unintended and costly side effects.</span></span> <span data-ttu-id="50fff-129">新功能/修补变得更加棘手、耗时且成本高昂。</span><span class="sxs-lookup"><span data-stu-id="50fff-129">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span> <span data-ttu-id="50fff-130">更新需要大量测试。</span><span class="sxs-lookup"><span data-stu-id="50fff-130">Updates require extensive testing.</span></span> <span data-ttu-id="50fff-131">耦合还使得重构组件或在替代实现中交换很困难。</span><span class="sxs-lookup"><span data-stu-id="50fff-131">Coupling also makes it difficult to refactor components or swap in alternative implementations.</span></span> <span data-ttu-id="50fff-132">即使是在构建时考虑到了严格的关注点，体系结构 erosion 也会在中设置为具有永不结束 "特殊事例" 的单一基本代码。</span><span class="sxs-lookup"><span data-stu-id="50fff-132">Even when constructed with a strict separation of concerns, architectural erosion sets in as the monolithic code base deteriorates with never-ending "special cases."</span></span>

### <a name="platform-lock-in"></a><span data-ttu-id="50fff-133">平台锁定</span><span class="sxs-lookup"><span data-stu-id="50fff-133">Platform lock-in</span></span>

<span data-ttu-id="50fff-134">单一应用程序是使用单个技术堆栈构造的。</span><span class="sxs-lookup"><span data-stu-id="50fff-134">A monolithic application is constructed with a single technology stack.</span></span> <span data-ttu-id="50fff-135">提供一致性时，这种承诺可能会成为创新的障碍。</span><span class="sxs-lookup"><span data-stu-id="50fff-135">While offering uniformity, this commitment can become a barrier to innovation.</span></span> <span data-ttu-id="50fff-136">新功能和组件将使用应用程序的当前堆栈生成-即使更多新式技术可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="50fff-136">New features and components will be built using the application's current stack - even when more modern technologies may be a better choice.</span></span> <span data-ttu-id="50fff-137">更长期的风险是技术堆栈过时和过时。</span><span class="sxs-lookup"><span data-stu-id="50fff-137">A longer-term risk is your technology stack becoming outdated and obsolete.</span></span> <span data-ttu-id="50fff-138">将整个应用程序重新架构到新的、更新式的平台，这一工作既昂贵又有风险。</span><span class="sxs-lookup"><span data-stu-id="50fff-138">Rearchitecting an entire application to a new, more modern platform is at best expensive and risky.</span></span>

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a><span data-ttu-id="50fff-139">容器和协调器的好处是什么？</span><span class="sxs-lookup"><span data-stu-id="50fff-139">What are the benefits of containers and orchestrators?</span></span>

<span data-ttu-id="50fff-140">第1章介绍了容器。</span><span class="sxs-lookup"><span data-stu-id="50fff-140">We introduced containers in Chapter 1.</span></span> <span data-ttu-id="50fff-141">我们重点介绍了云本机计算基础（CNCF）如何将容器化作为其[云本机线索映射](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png)指南的第一步，使企业开始实现云本机旅程。</span><span class="sxs-lookup"><span data-stu-id="50fff-141">We highlighted how the Cloud Native Computing Foundation (CNCF) ranks containerization as the first step in their [Cloud-Native Trail Map](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) - guidance for enterprises beginning their cloud-native journey.</span></span> <span data-ttu-id="50fff-142">在本部分中，我们将介绍容器的优点。</span><span class="sxs-lookup"><span data-stu-id="50fff-142">In this section, we discuss the benefits of containers.</span></span>

<span data-ttu-id="50fff-143">Docker 是最常用的容器管理平台。</span><span class="sxs-lookup"><span data-stu-id="50fff-143">Docker is the most popular container management platform.</span></span> <span data-ttu-id="50fff-144">它可与 Linux 或 Windows 上的容器一起使用。</span><span class="sxs-lookup"><span data-stu-id="50fff-144">It works with containers on both Linux or Windows.</span></span> <span data-ttu-id="50fff-145">容器提供独立但可重复的应用程序环境，这些环境在任何系统上以相同的方式运行。</span><span class="sxs-lookup"><span data-stu-id="50fff-145">Containers provide separate but reproducible application environments that run the same way on any system.</span></span> <span data-ttu-id="50fff-146">这一方面使它们完美地用于开发和托管云本机服务。</span><span class="sxs-lookup"><span data-stu-id="50fff-146">This aspect makes them perfect for developing and hosting cloud-native services.</span></span> <span data-ttu-id="50fff-147">容器彼此隔离。</span><span class="sxs-lookup"><span data-stu-id="50fff-147">Containers are isolated from one another.</span></span> <span data-ttu-id="50fff-148">同一主机硬件上的两个容器可以具有不同版本的软件，而不会导致冲突。</span><span class="sxs-lookup"><span data-stu-id="50fff-148">Two containers on the same host hardware can have different versions of software, without causing conflicts.</span></span>

<span data-ttu-id="50fff-149">容器由简单的基于文本的文件定义，这些文件将变为项目项目并签入到源代码管理中。</span><span class="sxs-lookup"><span data-stu-id="50fff-149">Containers are defined by simple text-based files that become project artifacts and are checked into source control.</span></span> <span data-ttu-id="50fff-150">尽管完全服务器和虚拟机需要手动操作才能进行更新，但容器非常易于控制版本。</span><span class="sxs-lookup"><span data-stu-id="50fff-150">While full servers and virtual machines require manual effort to update, containers are easily version-controlled.</span></span> <span data-ttu-id="50fff-151">可使用自动工具作为生成管道的一部分，开发、测试和部署在容器中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="50fff-151">Apps built to run in containers can be developed, tested, and deployed using automated tools as part of a build pipeline.</span></span>

<span data-ttu-id="50fff-152">容器是不可变的。</span><span class="sxs-lookup"><span data-stu-id="50fff-152">Containers are immutable.</span></span> <span data-ttu-id="50fff-153">定义容器后，可以完全相同的方式重新创建和运行。</span><span class="sxs-lookup"><span data-stu-id="50fff-153">Once you define a container, you can recreate and run it exactly the same way.</span></span> <span data-ttu-id="50fff-154">这种不可变性适用于基于组件的设计。</span><span class="sxs-lookup"><span data-stu-id="50fff-154">This immutability lends itself to component-based design.</span></span> <span data-ttu-id="50fff-155">如果应用程序的某些部分的演化不同于其他部分，那么当你只是部署最常发生变化的部件时，为什么会重新部署整个应用？</span><span class="sxs-lookup"><span data-stu-id="50fff-155">If some parts of an application evolve differently than others, why redeploy the entire app when you can just deploy the parts that change most frequently?</span></span> <span data-ttu-id="50fff-156">应用的不同功能和交叉切削问题可以分解为单独的单位。</span><span class="sxs-lookup"><span data-stu-id="50fff-156">Different features and cross-cutting concerns of an app can be broken up into separate units.</span></span> <span data-ttu-id="50fff-157">图3-2 显示了单一应用程序如何通过委托某些功能来利用容器和微服务。</span><span class="sxs-lookup"><span data-stu-id="50fff-157">Figure 3-2 shows how a monolithic app can take advantage of containers and microservices by delegating certain features or functionality.</span></span> <span data-ttu-id="50fff-158">应用程序本身中的其余功能也已容器化。</span><span class="sxs-lookup"><span data-stu-id="50fff-158">The remaining functionality in the app itself has also been containerized.</span></span>

<span data-ttu-id="50fff-159">![分解单一应用程序以在后端使用微服务。](./media/breaking-up-monolith-with-backend-microservices.png)
**图 3-2**。</span><span class="sxs-lookup"><span data-stu-id="50fff-159">![Breaking up a monolithic app to use microservices in the back end.](./media/breaking-up-monolith-with-backend-microservices.png)
**Figure 3-2**.</span></span> <span data-ttu-id="50fff-160">分解单一应用程序以在后端使用微服务。</span><span class="sxs-lookup"><span data-stu-id="50fff-160">Breaking up a monolithic app to use microservices in the back end.</span></span>

<span data-ttu-id="50fff-161">每个云本机服务都在单独的容器中生成和部署。</span><span class="sxs-lookup"><span data-stu-id="50fff-161">Each cloud-native service is built and deployed in a separate container.</span></span> <span data-ttu-id="50fff-162">每个都可以根据需要进行更新。</span><span class="sxs-lookup"><span data-stu-id="50fff-162">Each can update as needed.</span></span> <span data-ttu-id="50fff-163">可以在节点上托管单个服务，每个服务都有相应的资源。</span><span class="sxs-lookup"><span data-stu-id="50fff-163">Individual services can be hosted on nodes with resources appropriate to each service.</span></span> <span data-ttu-id="50fff-164">每个服务的运行环境是不可变的，在开发、测试和生产环境之间共享，并且易于版本化。</span><span class="sxs-lookup"><span data-stu-id="50fff-164">The environment each service runs in is immutable, shared across dev, test, and production environments, and easily versioned.</span></span> <span data-ttu-id="50fff-165">应用程序的不同区域之间的耦合与服务间的调用或消息（而不是单体架构中的编译时依赖关系）显式发生。</span><span class="sxs-lookup"><span data-stu-id="50fff-165">Coupling between different areas of the application occurs explicitly as calls or messages between services, not compile-time dependencies within the monolith.</span></span> <span data-ttu-id="50fff-166">你还可以选择最能充分利用给定功能的技术，无需更改应用程序的其余部分。</span><span class="sxs-lookup"><span data-stu-id="50fff-166">You can also choose the technology that best suites a given capability without requiring changes to the rest of the app.</span></span>

<span data-ttu-id="50fff-167">容器化服务需要自动管理。</span><span class="sxs-lookup"><span data-stu-id="50fff-167">Containerized services require automated management.</span></span> <span data-ttu-id="50fff-168">手动管理一大组独立部署的容器是不可行的。</span><span class="sxs-lookup"><span data-stu-id="50fff-168">It wouldn't be feasible to manually administer a large set of independently deployed containers.</span></span> <span data-ttu-id="50fff-169">例如，请考虑以下任务：</span><span class="sxs-lookup"><span data-stu-id="50fff-169">For example, consider the following tasks:</span></span>

- <span data-ttu-id="50fff-170">如何在多台计算机的群集中预配容器实例？</span><span class="sxs-lookup"><span data-stu-id="50fff-170">How will container instances be provisioned across a cluster of many machines?</span></span>
- <span data-ttu-id="50fff-171">部署完成后，容器的发现和通信方式如何呢？</span><span class="sxs-lookup"><span data-stu-id="50fff-171">Once deployed, how will containers discover and communicate with each other?</span></span>
- <span data-ttu-id="50fff-172">容器如何按需进行缩放？</span><span class="sxs-lookup"><span data-stu-id="50fff-172">How can containers scale in or out on-demand?</span></span>
- <span data-ttu-id="50fff-173">如何监视每个容器的运行状况？</span><span class="sxs-lookup"><span data-stu-id="50fff-173">How do you monitor the health of each container?</span></span>
- <span data-ttu-id="50fff-174">如何针对硬件和软件故障保护容器？</span><span class="sxs-lookup"><span data-stu-id="50fff-174">How do you protect a container against hardware and software failures?</span></span>
- <span data-ttu-id="50fff-175">如何将实时应用程序的容器升级到零停机时间？</span><span class="sxs-lookup"><span data-stu-id="50fff-175">How do upgrade containers for a live application with zero downtime?</span></span>

<span data-ttu-id="50fff-176">容器协调器解决这些问题和其他问题。</span><span class="sxs-lookup"><span data-stu-id="50fff-176">Container orchestrators address and automate these and other concerns.</span></span>

<span data-ttu-id="50fff-177">在云中，Kubernetes 已成为事实容器 orchestrator。</span><span class="sxs-lookup"><span data-stu-id="50fff-177">In the cloud-native eco-system, Kubernetes has become the de facto container orchestrator.</span></span> <span data-ttu-id="50fff-178">它是由云本机计算基础（CNCF）管理的开源平台。</span><span class="sxs-lookup"><span data-stu-id="50fff-178">It's an open-source platform managed by the Cloud Native Computing Foundation (CNCF).</span></span> <span data-ttu-id="50fff-179">Kubernetes 自动化了计算机群集上容器化工作负荷的部署、缩放和操作问题。</span><span class="sxs-lookup"><span data-stu-id="50fff-179">Kubernetes automates the deployment, scaling, and operational concerns of containerized workloads across a machine cluster.</span></span> <span data-ttu-id="50fff-180">但是，安装和管理 Kubernetes 非常复杂。</span><span class="sxs-lookup"><span data-stu-id="50fff-180">However, installing and managing Kubernetes is notoriously complex.</span></span>

<span data-ttu-id="50fff-181">更好的方法是使用 Kubernetes 作为云供应商提供的托管服务。</span><span class="sxs-lookup"><span data-stu-id="50fff-181">A much better approach is to leverage Kubernetes as a managed service from a cloud vendor.</span></span> <span data-ttu-id="50fff-182">Azure 云的功能是一个完全托管的 Kubernetes 平台，该平台名为[Azure Kubernetes Service （AKS）](https://azure.microsoft.com/services/kubernetes-service/)。</span><span class="sxs-lookup"><span data-stu-id="50fff-182">The Azure cloud features a fully managed Kubernetes platform entitled [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/).</span></span> <span data-ttu-id="50fff-183">AKS 抽象了管理 Kubernetes 的复杂性和操作开销。</span><span class="sxs-lookup"><span data-stu-id="50fff-183">AKS abstracts the complexity and operational overhead of managing Kubernetes.</span></span> <span data-ttu-id="50fff-184">使用 Kubernetes 作为云服务;Microsoft 负责管理和支持它。</span><span class="sxs-lookup"><span data-stu-id="50fff-184">You consume Kubernetes as a cloud service; Microsoft takes responsibility for managing and supporting it.</span></span> <span data-ttu-id="50fff-185">AKS 还与其他 Azure 服务和开发工具紧密集成。</span><span class="sxs-lookup"><span data-stu-id="50fff-185">AKS also tightly integrates with other Azure services and dev tools.</span></span>

<span data-ttu-id="50fff-186">AKS 是一种基于群集的技术。</span><span class="sxs-lookup"><span data-stu-id="50fff-186">AKS is a cluster-based technology.</span></span> <span data-ttu-id="50fff-187">联合虚拟机或节点的池部署到 Azure 云。</span><span class="sxs-lookup"><span data-stu-id="50fff-187">A pool of federated virtual machines, or nodes, is deployed to the Azure cloud.</span></span> <span data-ttu-id="50fff-188">它们共同构成了一个高度可用的环境或群集。</span><span class="sxs-lookup"><span data-stu-id="50fff-188">Together they form a highly available environment, or cluster.</span></span> <span data-ttu-id="50fff-189">群集将作为无缝的单一实体出现到你的云本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="50fff-189">The cluster appears as a seamless, single entity to your cloud-native application.</span></span> <span data-ttu-id="50fff-190">在这种情况下，AKS 会按照均匀分布负载的预定义策略，在这些节点上部署容器化服务。</span><span class="sxs-lookup"><span data-stu-id="50fff-190">Under the hood, AKS deploys your containerized services across these nodes following a predefined strategy that evenly distributes the load.</span></span>

## <a name="what-are-the-scaling-benefits"></a><span data-ttu-id="50fff-191">缩放的优点是什么？</span><span class="sxs-lookup"><span data-stu-id="50fff-191">What are the scaling benefits?</span></span>

<span data-ttu-id="50fff-192">基于容器构建的服务可以利用 Kubernetes 等业务流程工具提供的缩放权益。</span><span class="sxs-lookup"><span data-stu-id="50fff-192">Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes.</span></span> <span data-ttu-id="50fff-193">设计容器仅知道自己的情况。</span><span class="sxs-lookup"><span data-stu-id="50fff-193">By design containers only know about themselves.</span></span> <span data-ttu-id="50fff-194">如果有多个需要协同工作的容器，则应将其组织在更高的级别。</span><span class="sxs-lookup"><span data-stu-id="50fff-194">Once you have multiple containers that need to work together, you should organize them at a higher level.</span></span> <span data-ttu-id="50fff-195">组织大量的容器及其共享依赖项（如网络配置）是业务流程工具在其中节省时间的地方！</span><span class="sxs-lookup"><span data-stu-id="50fff-195">Organizing large numbers of containers and their shared dependencies, such as network configuration, is where orchestration tools come in to save the day!</span></span> <span data-ttu-id="50fff-196">Kubernetes 在一组容器上创建一个抽象层，然后将它们*组织到 pod*。</span><span class="sxs-lookup"><span data-stu-id="50fff-196">Kubernetes creates an abstraction layer over groups of containers and organizes them into *pods*.</span></span> <span data-ttu-id="50fff-197">Pod 在称为*节点*的辅助角色计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="50fff-197">Pods run on worker machines referred to as *nodes*.</span></span> <span data-ttu-id="50fff-198">此组织结构称为*群集*。</span><span class="sxs-lookup"><span data-stu-id="50fff-198">This organized structure is referred to as a *cluster*.</span></span> <span data-ttu-id="50fff-199">图3-3 显示了 Kubernetes 群集的不同组件。</span><span class="sxs-lookup"><span data-stu-id="50fff-199">Figure 3-3 shows the different components of a Kubernetes cluster.</span></span>

<span data-ttu-id="50fff-200">![Kubernetes 群集组件。](./media/kubernetes-cluster-components.png)
**图 3-3**。</span><span class="sxs-lookup"><span data-stu-id="50fff-200">![Kubernetes cluster components.](./media/kubernetes-cluster-components.png)
**Figure 3-3**.</span></span> <span data-ttu-id="50fff-201">Kubernetes 群集组件。</span><span class="sxs-lookup"><span data-stu-id="50fff-201">Kubernetes cluster components.</span></span>

<span data-ttu-id="50fff-202">缩放容器化工作负荷是容器协调器的一项重要功能。</span><span class="sxs-lookup"><span data-stu-id="50fff-202">Scaling containerized workloads is a key feature of container orchestrators.</span></span> <span data-ttu-id="50fff-203">AKS 支持跨两个维度的自动缩放：容器实例和计算节点。</span><span class="sxs-lookup"><span data-stu-id="50fff-203">AKS supports automatic scaling across two dimensions: Container instances and compute nodes.</span></span> <span data-ttu-id="50fff-204">它们共同使 AKS 能够快速有效地响应需求高峰并增加额外资源。</span><span class="sxs-lookup"><span data-stu-id="50fff-204">Together they give AKS the ability to quickly and efficiently respond to spikes in demand and add additional resources.</span></span> <span data-ttu-id="50fff-205">本章稍后将讨论 AKS 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="50fff-205">We discuss scaling in AKS later in this chapter.</span></span>

### <a name="declarative-versus-imperative"></a><span data-ttu-id="50fff-206">声明性与命令式</span><span class="sxs-lookup"><span data-stu-id="50fff-206">Declarative versus imperative</span></span>

<span data-ttu-id="50fff-207">Kubernetes 支持声明性和命令性配置。</span><span class="sxs-lookup"><span data-stu-id="50fff-207">Kubernetes supports both declarative and imperative configuration.</span></span> <span data-ttu-id="50fff-208">命令式方法涉及运行各种命令，这些命令告诉 Kubernetes 如何执行每个步骤。</span><span class="sxs-lookup"><span data-stu-id="50fff-208">The imperative approach involves running various commands that tell Kubernetes what to do each step of the way.</span></span> <span data-ttu-id="50fff-209">运行此映像。</span><span class="sxs-lookup"><span data-stu-id="50fff-209">Run this image.</span></span> <span data-ttu-id="50fff-210">删除此 pod。</span><span class="sxs-lookup"><span data-stu-id="50fff-210">Delete this pod.</span></span> <span data-ttu-id="50fff-211">公开此端口。</span><span class="sxs-lookup"><span data-stu-id="50fff-211">Expose this port.</span></span> <span data-ttu-id="50fff-212">使用声明性方法，你可以创建一个名为清单的配置文件，以描述你需要的内容，而不是要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="50fff-212">With the declarative approach, you create a configuration file, called a manifest, to describe what you want instead of what to do.</span></span> <span data-ttu-id="50fff-213">Kubernetes 读取清单并将所需的结束状态转换为实际结束状态。</span><span class="sxs-lookup"><span data-stu-id="50fff-213">Kubernetes reads the manifest and transforms your desired end state into actual end state.</span></span>

<span data-ttu-id="50fff-214">命令性命令非常适用于学习和交互式试验。</span><span class="sxs-lookup"><span data-stu-id="50fff-214">Imperative commands are great for learning and interactive experimentation.</span></span> <span data-ttu-id="50fff-215">但是，你将需要以声明方式创建 Kubernetes 清单文件，以将基础结构作为代码方法，从而提供可靠且可重复的部署。</span><span class="sxs-lookup"><span data-stu-id="50fff-215">However, you'll want to declaratively create Kubernetes manifest files to embrace an infrastructure as code approach, providing for reliable and repeatable deployments.</span></span> <span data-ttu-id="50fff-216">清单文件将成为项目项目，并在 CI/CD 管道中用于自动执行 Kubernetes 部署。</span><span class="sxs-lookup"><span data-stu-id="50fff-216">The manifest file becomes a project artifact and is used in your CI/CD pipeline for automating Kubernetes deployments.</span></span>

<span data-ttu-id="50fff-217">如果已使用命令性命令配置了群集，则可以使用`kubectl get svc SERVICENAME -o yaml > service.yaml`导出声明性清单。</span><span class="sxs-lookup"><span data-stu-id="50fff-217">If you've already configured your cluster using imperative commands, you can export a declarative manifest by using `kubectl get svc SERVICENAME -o yaml > service.yaml`.</span></span> <span data-ttu-id="50fff-218">此命令生成类似于下面所示的清单：</span><span class="sxs-lookup"><span data-stu-id="50fff-218">This command produces a manifest similar to one shown below:</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: "2019-09-13T13:58:47Z"
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "153"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 9b1fac62-d62e-11e9-8968-00155d38010d
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 6443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

<span data-ttu-id="50fff-219">使用声明性配置时，你可以在使用配置文件所在的文件夹上使用`kubectl diff -f FOLDERNAME`来预览将进行的更改。</span><span class="sxs-lookup"><span data-stu-id="50fff-219">When using declarative configuration, you can preview the changes that will be made before committing them by using `kubectl diff -f FOLDERNAME` against the folder where your configuration files are located.</span></span> <span data-ttu-id="50fff-220">确定要应用所做的更改后，运行`kubectl apply -f FOLDERNAME`。</span><span class="sxs-lookup"><span data-stu-id="50fff-220">Once you're sure you want to apply the changes, run `kubectl apply -f FOLDERNAME`.</span></span> <span data-ttu-id="50fff-221">添加`-R`以递归方式处理文件夹层次结构。</span><span class="sxs-lookup"><span data-stu-id="50fff-221">Add `-R` to recursively process a folder hierarchy.</span></span>

<span data-ttu-id="50fff-222">你还可以将声明性配置用于其他 Kubernetes 功能，其中一项是部署。</span><span class="sxs-lookup"><span data-stu-id="50fff-222">You can also use declarative configuration with other Kubernetes features, one of which being deployments.</span></span> <span data-ttu-id="50fff-223">声明性部署可帮助管理版本、更新和缩放。</span><span class="sxs-lookup"><span data-stu-id="50fff-223">Declarative deployments help manage releases, updates, and scaling.</span></span> <span data-ttu-id="50fff-224">它们指示 Kubernetes 部署控制器如何部署新更改、扩大负载或回滚到以前的修订版本。</span><span class="sxs-lookup"><span data-stu-id="50fff-224">They instruct the Kubernetes deployment controller on how to deploy new changes, scale out load, or roll back to a previous revision.</span></span> <span data-ttu-id="50fff-225">如果群集不稳定，则声明性部署会自动将群集恢复到所需状态。</span><span class="sxs-lookup"><span data-stu-id="50fff-225">If a cluster is unstable, a declarative deployment will automatically return the cluster back to a desired state.</span></span> <span data-ttu-id="50fff-226">例如，如果某个节点出现故障，部署机制将重新部署替代以实现所需状态</span><span class="sxs-lookup"><span data-stu-id="50fff-226">For example, if a node should crash, the deployment mechanism will redeploy a replacement to achieve your desired state</span></span>

<span data-ttu-id="50fff-227">使用声明性配置，可将基础结构表示为可签入并在应用程序代码中进行版本控制的代码。</span><span class="sxs-lookup"><span data-stu-id="50fff-227">Using declarative configuration allows infrastructure to be represented as code that can be checked in and versioned alongside the application code.</span></span> <span data-ttu-id="50fff-228">它通过生成和部署管道为连续部署提供改进的更改控制和更好的支持。</span><span class="sxs-lookup"><span data-stu-id="50fff-228">It provides improved change control and better support for continuous deployment using a build and deploy pipeline.</span></span>

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a><span data-ttu-id="50fff-229">哪些方案适用于容器和协调器？</span><span class="sxs-lookup"><span data-stu-id="50fff-229">What scenarios are ideal for containers and orchestrators?</span></span>

<span data-ttu-id="50fff-230">以下方案非常适合使用容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="50fff-230">The following scenarios are ideal for using containers and orchestrators.</span></span>

### <a name="applications-requiring-high-uptime-and-scalability"></a><span data-ttu-id="50fff-231">需要高运行时间和可伸缩性的应用程序</span><span class="sxs-lookup"><span data-stu-id="50fff-231">Applications requiring high uptime and scalability</span></span>

<span data-ttu-id="50fff-232">具有高运行时间和伸缩性要求的单个应用程序是使用微服务、容器和协调器的云本机体系结构的理想选择。</span><span class="sxs-lookup"><span data-stu-id="50fff-232">Individual applications that have high uptime and scalability requirements are ideal candidates for cloud-native architectures using microservices, containers, and orchestrators.</span></span> <span data-ttu-id="50fff-233">它们可在容器中进行开发，在版本控制环境中进行测试，并部署到生产环境中，但停机时间为零。</span><span class="sxs-lookup"><span data-stu-id="50fff-233">They can be developed in containers, tested across versioned environments, and deployed into production with zero downtime.</span></span> <span data-ttu-id="50fff-234">使用 Kubernetes 群集可确保这样的应用程序也可以按需缩放，并从节点故障中自动恢复。</span><span class="sxs-lookup"><span data-stu-id="50fff-234">The use of Kubernetes clusters ensures such apps can also scale on demand and recover automatically from node failures.</span></span>

### <a name="large-numbers-of-applications"></a><span data-ttu-id="50fff-235">大量应用程序</span><span class="sxs-lookup"><span data-stu-id="50fff-235">Large numbers of applications</span></span>

<span data-ttu-id="50fff-236">部署和维护大量应用程序的组织从容器和协调器中获益。</span><span class="sxs-lookup"><span data-stu-id="50fff-236">Organizations that deploy and maintain large numbers of applications benefit from containers and orchestrators.</span></span> <span data-ttu-id="50fff-237">设置容器化环境和 Kubernetes 群集的前期工作主要是一项固定成本。</span><span class="sxs-lookup"><span data-stu-id="50fff-237">The up front effort of setting up containerized environments and Kubernetes clusters is primarily a fixed cost.</span></span> <span data-ttu-id="50fff-238">部署、维护和更新单个应用程序的成本会因应用程序数量而异。</span><span class="sxs-lookup"><span data-stu-id="50fff-238">Deploying, maintaining, and updating individual applications has a cost that varies with the number of applications.</span></span> <span data-ttu-id="50fff-239">除了少量的应用程序，手动维护自定义应用程序的复杂性超出了使用容器和协调器实现解决方案的成本。</span><span class="sxs-lookup"><span data-stu-id="50fff-239">Beyond a small number of applications, the complexity of maintaining custom applications manually exceeds the cost of implementing a solution using containers and orchestrators.</span></span>

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a><span data-ttu-id="50fff-240">何时应避免使用容器和协调器？</span><span class="sxs-lookup"><span data-stu-id="50fff-240">When should you avoid using containers and orchestrators?</span></span>

<span data-ttu-id="50fff-241">如果无法按照十二因素应用程序原则构建你的应用程序，应考虑避免容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="50fff-241">If you're unable to build your application following the Twelve-Factor App principles, you should consider avoiding containers and orchestrators.</span></span> <span data-ttu-id="50fff-242">在这些情况下，请考虑基于 VM 的托管平台，或可能是某个混合系统。</span><span class="sxs-lookup"><span data-stu-id="50fff-242">In these cases, consider a VM-based hosting platform, or possibly some hybrid system.</span></span> <span data-ttu-id="50fff-243">利用它，你始终可以在单独的容器中或甚至无服务器的功能中关闭某些功能。</span><span class="sxs-lookup"><span data-stu-id="50fff-243">With it, you can always spin off certain pieces of functionality into separate containers or even serverless functions.</span></span>

## <a name="development-resources"></a><span data-ttu-id="50fff-244">开发资源</span><span class="sxs-lookup"><span data-stu-id="50fff-244">Development resources</span></span>

<span data-ttu-id="50fff-245">本部分显示了可帮助你开始使用容器和协调器作为下一个应用程序的开发资源的简短列表。</span><span class="sxs-lookup"><span data-stu-id="50fff-245">This section shows a short list of development resources that may help you get started using containers and orchestrators for your next application.</span></span> <span data-ttu-id="50fff-246">如果正在寻找有关如何设计云本机微服务体系结构应用的指南，请阅读此书籍的随附 .net[微服务：容器化 .Net 应用程序的体系结构](https://aka.ms/microservicesebook)。</span><span class="sxs-lookup"><span data-stu-id="50fff-246">If you're looking for guidance on how to design your cloud-native microservices architecture app, read this book's companion, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).</span></span>

### <a name="local-kubernetes-development"></a><span data-ttu-id="50fff-247">本地 Kubernetes 开发</span><span class="sxs-lookup"><span data-stu-id="50fff-247">Local Kubernetes Development</span></span>

<span data-ttu-id="50fff-248">Kubernetes 部署在生产环境中提供了极大的价值，但也可以在开发计算机上本地运行。</span><span class="sxs-lookup"><span data-stu-id="50fff-248">Kubernetes deployments provide great value in production environments, but can also run locally on your development machine.</span></span> <span data-ttu-id="50fff-249">尽管你可能会独立地处理单独的微服务，但有时你可能需要在本地运行整个系统，就像部署到生产环境时它会运行一样。</span><span class="sxs-lookup"><span data-stu-id="50fff-249">While you may work on individual microservices independently, there may be times when you'll need to run the entire system locally - just as it will run when deployed to production.</span></span> <span data-ttu-id="50fff-250">可以通过以下几种工具来帮助： Minikube 和 Docker 桌面。</span><span class="sxs-lookup"><span data-stu-id="50fff-250">There are several tools that can help: Minikube and Docker Desktop.</span></span> <span data-ttu-id="50fff-251">Visual Studio 还提供了用于 Docker 开发的工具。</span><span class="sxs-lookup"><span data-stu-id="50fff-251">Visual Studio also provides tooling for Docker development.</span></span>

### <a name="minikube"></a><span data-ttu-id="50fff-252">Minikube</span><span class="sxs-lookup"><span data-stu-id="50fff-252">Minikube</span></span>

<span data-ttu-id="50fff-253">什么是 Minikube？</span><span class="sxs-lookup"><span data-stu-id="50fff-253">What is Minikube?</span></span> <span data-ttu-id="50fff-254">Minikube 项目显示 "Minikube 在 macOS、Linux 和 Windows 上实现本地 Kubernetes 群集"。</span><span class="sxs-lookup"><span data-stu-id="50fff-254">The Minikube project says "Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows."</span></span> <span data-ttu-id="50fff-255">它的主要目标是 "成为本地 Kubernetes 应用程序开发的最佳工具，并支持所有适合的 Kubernetes 功能"。</span><span class="sxs-lookup"><span data-stu-id="50fff-255">Its primary goals are "to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit."</span></span> <span data-ttu-id="50fff-256">安装 Minikube 与 Docker 分离，但 Minikube 支持不同于 Docker Desktop 支持的虚拟机监控程序。</span><span class="sxs-lookup"><span data-stu-id="50fff-256">Installing Minikube is separate from Docker, but Minikube supports different hypervisors than Docker Desktop supports.</span></span> <span data-ttu-id="50fff-257">Minikube 目前支持以下 Kubernetes 功能：</span><span class="sxs-lookup"><span data-stu-id="50fff-257">The following Kubernetes features are currently supported by Minikube:</span></span>

- <span data-ttu-id="50fff-258">DNS</span><span class="sxs-lookup"><span data-stu-id="50fff-258">DNS</span></span>
- <span data-ttu-id="50fff-259">NodePorts</span><span class="sxs-lookup"><span data-stu-id="50fff-259">NodePorts</span></span>
- <span data-ttu-id="50fff-260">ConfigMaps 和机密</span><span class="sxs-lookup"><span data-stu-id="50fff-260">ConfigMaps and secrets</span></span>
- <span data-ttu-id="50fff-261">仪表板</span><span class="sxs-lookup"><span data-stu-id="50fff-261">Dashboards</span></span>
- <span data-ttu-id="50fff-262">容器运行时： Docker、rkt、CRI 和 containerd</span><span class="sxs-lookup"><span data-stu-id="50fff-262">Container runtimes: Docker, rkt, CRI-O, and containerd</span></span>
- <span data-ttu-id="50fff-263">启用容器网络接口（CNI）</span><span class="sxs-lookup"><span data-stu-id="50fff-263">Enabling Container Network Interface (CNI)</span></span>
- <span data-ttu-id="50fff-264">流入量</span><span class="sxs-lookup"><span data-stu-id="50fff-264">Ingress</span></span>

<span data-ttu-id="50fff-265">安装 Minikube 后，可以通过运行`minikube start`命令快速开始使用它，这会下载映像并启动本地 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="50fff-265">After installing Minikube, you can quickly start using it by running the `minikube start` command, which downloads an image and start the local Kubernetes cluster.</span></span> <span data-ttu-id="50fff-266">启动群集后，你可以使用标准 Kubernetes `kubectl`命令与它交互。</span><span class="sxs-lookup"><span data-stu-id="50fff-266">Once the cluster is started, you interact with it using the standard Kubernetes `kubectl` commands.</span></span>

### <a name="docker-desktop"></a><span data-ttu-id="50fff-267">Docker Desktop</span><span class="sxs-lookup"><span data-stu-id="50fff-267">Docker Desktop</span></span>

<span data-ttu-id="50fff-268">你还可以直接从 Windows 上的 Docker Desktop 使用 Kubernetes。</span><span class="sxs-lookup"><span data-stu-id="50fff-268">You can also work with Kubernetes directly from Docker Desktop on Windows.</span></span> <span data-ttu-id="50fff-269">如果你使用的是 Windows 容器，则这是唯一的选择，对于非 Windows 容器也是不错的选择。</span><span class="sxs-lookup"><span data-stu-id="50fff-269">It is your only option if you're using Windows Containers, and is a great choice for non-Windows containers as well.</span></span> <span data-ttu-id="50fff-270">图3-4 显示了如何在运行 Docker Desktop 时启用本地 Kubernetes 支持。</span><span class="sxs-lookup"><span data-stu-id="50fff-270">Figure 3-4 shows how to enable local Kubernetes support when running Docker Desktop.</span></span>

![在 Docker Desktop 中配置 Kubernetes](./media/docker-desktop-kubernetes.png)

<span data-ttu-id="50fff-272">**图 3-4**。</span><span class="sxs-lookup"><span data-stu-id="50fff-272">**Figure 3-4**.</span></span> <span data-ttu-id="50fff-273">在 Docker Desktop 中配置 Kubernetes。</span><span class="sxs-lookup"><span data-stu-id="50fff-273">Configuring Kubernetes in Docker Desktop.</span></span>

<span data-ttu-id="50fff-274">Docker Desktop 是在本地配置和运行容器化应用程序的最常用工具。</span><span class="sxs-lookup"><span data-stu-id="50fff-274">Docker Desktop is the most popular tool for configuring and running containerized apps locally.</span></span> <span data-ttu-id="50fff-275">使用 Docker Desktop 时，可以针对将部署到生产环境中的一组 Docker 容器映像进行本地开发。</span><span class="sxs-lookup"><span data-stu-id="50fff-275">When you work with Docker Desktop, you can develop locally against the exact same set of Docker container images that you'll deploy to production.</span></span> <span data-ttu-id="50fff-276">Docker Desktop 设计为在本地生成、测试和交付容器化应用。</span><span class="sxs-lookup"><span data-stu-id="50fff-276">Docker Desktop is designed to "build, test, and ship" containerized apps locally.</span></span> <span data-ttu-id="50fff-277">它支持 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="50fff-277">It supports both Linux and Windows containers.</span></span> <span data-ttu-id="50fff-278">将映像推送到映像注册表（如 Azure 容器注册表或 Docker 中心）后，AKS 可将其提取并部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="50fff-278">Once you push your images to an image registry, like Azure Container Registry or Docker Hub, AKS can pull and deploy them to production.</span></span>

### <a name="visual-studio-docker-tooling"></a><span data-ttu-id="50fff-279">Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="50fff-279">Visual Studio Docker Tooling</span></span>

<span data-ttu-id="50fff-280">Visual Studio 支持基于 web 的应用程序的 Docker 开发。</span><span class="sxs-lookup"><span data-stu-id="50fff-280">Visual Studio supports Docker development for web-based applications.</span></span> <span data-ttu-id="50fff-281">创建新的 ASP.NET Core 应用程序时，可以选择使用 Docker 支持来配置该应用程序，如图3-5 所示。</span><span class="sxs-lookup"><span data-stu-id="50fff-281">When you create a new ASP.NET Core application, you have an option to configure it with Docker support, as shown in Figure 3-5.</span></span>

![Visual Studio 启用 Docker 支持](./media/visual-studio-enable-docker-support.png)

<span data-ttu-id="50fff-283">**图 3-5**。</span><span class="sxs-lookup"><span data-stu-id="50fff-283">**Figure 3-5**.</span></span> <span data-ttu-id="50fff-284">Visual Studio 启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="50fff-284">Visual Studio Enable Docker Support</span></span>

<span data-ttu-id="50fff-285">如果选择此选项，则会`Dockerfile`在其根中创建项目，该项目可用于在 Docker 容器中生成和托管应用。</span><span class="sxs-lookup"><span data-stu-id="50fff-285">When this option is selected, the project is created with a `Dockerfile` in its root, which can be used to build and host the app in a Docker container.</span></span> <span data-ttu-id="50fff-286">图 3-6 中显示了一个示例 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="50fff-286">An example Dockerfile is shown in Figure 3-6.git</span></span>

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.0-stretch AS build
WORKDIR /src
COPY ["WebApplication3/WebApplication3.csproj", "WebApplication3/"]
RUN dotnet restore "WebApplication3/WebApplication3.csproj"
COPY . .
WORKDIR "/src/WebApplication3"
RUN dotnet build "WebApplication3.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication3.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication3.dll"]
```

<span data-ttu-id="50fff-287">**图 3-6**。</span><span class="sxs-lookup"><span data-stu-id="50fff-287">**Figure 3-6**.</span></span> <span data-ttu-id="50fff-288">Visual Studio 生成的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="50fff-288">Visual Studio generated Dockerfile</span></span>

<span data-ttu-id="50fff-289">应用运行时的默认行为也配置为使用 Docker。</span><span class="sxs-lookup"><span data-stu-id="50fff-289">The default behavior when the app runs is configured to use Docker as well.</span></span> <span data-ttu-id="50fff-290">图3-7 显示了在添加 Docker 支持创建的新 ASP.NET Core 项目中可用的不同运行选项。</span><span class="sxs-lookup"><span data-stu-id="50fff-290">Figure 3-7 shows the different run options available from a new ASP.NET Core project created with Docker support added.</span></span>

![Visual Studio Docker 运行选项](./media/visual-studio-docker-run-options.png)

<span data-ttu-id="50fff-292">**图 3-7**。</span><span class="sxs-lookup"><span data-stu-id="50fff-292">**Figure 3-7**.</span></span> <span data-ttu-id="50fff-293">Visual Studio Docker 运行选项</span><span class="sxs-lookup"><span data-stu-id="50fff-293">Visual Studio Docker Run Options</span></span>

<span data-ttu-id="50fff-294">除了本地开发外， [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/)为多个开发人员提供了一种方便的方法，以便在 Azure 中使用自己的 Kubernetes 配置。</span><span class="sxs-lookup"><span data-stu-id="50fff-294">In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way for multiple developers to work with their own Kubernetes configurations within Azure.</span></span> <span data-ttu-id="50fff-295">如图3-7 所示，还可以在 Azure Dev Spaces 中运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="50fff-295">As you can see in Figure 3-7, you can also run the application in Azure Dev Spaces.</span></span>

<span data-ttu-id="50fff-296">此外，随时可以向现有 ASP.NET Core 应用程序添加 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="50fff-296">Also, at any time you can add Docker support to an existing ASP.NET Core application.</span></span> <span data-ttu-id="50fff-297">在 Visual Studio 解决方案资源管理器中，右键单击项目并**添加** > **Docker 支持**，如图3-8 所示。</span><span class="sxs-lookup"><span data-stu-id="50fff-297">From the Visual Studio Solution Explorer, right click on the project and **Add** > **Docker Support**, as shown in Figure 3-8.</span></span>

![Visual Studio 添加 Docker 支持](./media/visual-studio-add-docker-support.png)

<span data-ttu-id="50fff-299">**图 3-8**。</span><span class="sxs-lookup"><span data-stu-id="50fff-299">**Figure 3-8**.</span></span> <span data-ttu-id="50fff-300">Visual Studio 添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="50fff-300">Visual Studio Add Docker Support</span></span>

<span data-ttu-id="50fff-301">还可以添加容器业务流程支持，如图3-8 所示。</span><span class="sxs-lookup"><span data-stu-id="50fff-301">You can also add Container Orchestration Support, also shown in Figure 3-8.</span></span> <span data-ttu-id="50fff-302">默认情况下，orchestrator 将使用 Kubernetes 和 Helm。</span><span class="sxs-lookup"><span data-stu-id="50fff-302">By default, the orchestrator uses Kubernetes and Helm.</span></span> <span data-ttu-id="50fff-303">选择 orchestrator 后，会将一个`azds.yaml`文件添加到项目根，并添加一个`charts`文件夹，其中包含用于配置应用程序并将其部署到 Kubernetes 的 Helm 图表。</span><span class="sxs-lookup"><span data-stu-id="50fff-303">Once you've chosen the orchestrator, a `azds.yaml` file is added to the project root and a `charts` folder is added containing the Helm charts used to configure and deploy the application to Kubernetes.</span></span> <span data-ttu-id="50fff-304">图3-9 显示新项目中生成的文件。</span><span class="sxs-lookup"><span data-stu-id="50fff-304">Figure 3-9 shows the resulting files in a new project.</span></span>

![Visual Studio 添加 Orchestrator 支持](./media/visual-studio-add-orchestrator-support.png)

<span data-ttu-id="50fff-306">**图 3-9**。</span><span class="sxs-lookup"><span data-stu-id="50fff-306">**Figure 3-9**.</span></span> <span data-ttu-id="50fff-307">Visual Studio 添加 Orchestrator 支持</span><span class="sxs-lookup"><span data-stu-id="50fff-307">Visual Studio Add Orchestrator Support</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="50fff-308">[上一页](scale-applications.md)
>[下一页](leverage-serverless-functions.md)</span><span class="sxs-lookup"><span data-stu-id="50fff-308">[Previous](scale-applications.md)
[Next](leverage-serverless-functions.md)</span></span>
