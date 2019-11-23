---
title: 利用容器和协调器
description: 利用 Azure 中的 Docker 容器和 Kubernetes 协调器
ms.date: 06/30/2019
ms.openlocfilehash: 7b136ed2760ea471f42ff82d20298ff8714c6dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841761"
---
# <a name="leveraging-containers-and-orchestrators"></a><span data-ttu-id="cf991-103">利用容器和协调器</span><span class="sxs-lookup"><span data-stu-id="cf991-103">Leveraging containers and orchestrators</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="cf991-104">容器和协调器旨在解决单一部署方法常见的问题。</span><span class="sxs-lookup"><span data-stu-id="cf991-104">Containers and orchestrators are designed to solve problems common to monolithic deployment approaches.</span></span>

## <a name="challenges-with-monolithic-deployments"></a><span data-ttu-id="cf991-105">单一部署难题</span><span class="sxs-lookup"><span data-stu-id="cf991-105">Challenges with monolithic deployments</span></span>

<span data-ttu-id="cf991-106">传统上，大多数应用程序都部署为单个单元。</span><span class="sxs-lookup"><span data-stu-id="cf991-106">Traditionally, most applications have been deployed as a single unit.</span></span> <span data-ttu-id="cf991-107">此类应用程序称为单体架构。</span><span class="sxs-lookup"><span data-stu-id="cf991-107">Such applications are referred to as a monolith.</span></span> <span data-ttu-id="cf991-108">这种将应用程序作为单一单元进行部署的通用方法，即使它们由多个模块或程序集组成，也称为单片体系结构，如图3-1 所示。</span><span class="sxs-lookup"><span data-stu-id="cf991-108">This general approach of deploying applications as single units even if they're composed of multiple modules or assemblies is known as monolithic architecture, as shown in Figure 3-1.</span></span>

![整体体系结构。](./media/monolithic-architecture.png)

<span data-ttu-id="cf991-110">**图 3-1**。</span><span class="sxs-lookup"><span data-stu-id="cf991-110">**Figure 3-1**.</span></span> <span data-ttu-id="cf991-111">整体体系结构。</span><span class="sxs-lookup"><span data-stu-id="cf991-111">Monolithic architecture.</span></span>

<span data-ttu-id="cf991-112">尽管它们具有简易性的优点，但单一体系结构面临着许多挑战：</span><span class="sxs-lookup"><span data-stu-id="cf991-112">Although they have the benefit of simplicity, monolithic architectures face a number of challenges:</span></span>

### <a name="deployments"></a><span data-ttu-id="cf991-113">部署</span><span class="sxs-lookup"><span data-stu-id="cf991-113">Deployments</span></span>

<span data-ttu-id="cf991-114">部署到单一应用程序通常需要重新启动整个应用程序，即使只替换一个小模块。</span><span class="sxs-lookup"><span data-stu-id="cf991-114">Deploying to monolithic applications typically requires restarting the entire application, even if only one small module is being replaced.</span></span> <span data-ttu-id="cf991-115">根据托管应用程序的计算机的数目，这可能会导致部署期间停机。</span><span class="sxs-lookup"><span data-stu-id="cf991-115">Depending on the number of machines hosting the application, this can result in downtime during deployments.</span></span>

### <a name="hosting"></a><span data-ttu-id="cf991-116">托管</span><span class="sxs-lookup"><span data-stu-id="cf991-116">Hosting</span></span>

<span data-ttu-id="cf991-117">整体应用程序完全承载于单个计算机实例上。</span><span class="sxs-lookup"><span data-stu-id="cf991-117">Monolithic applications are hosted entirely on a single machine instance.</span></span> <span data-ttu-id="cf991-118">这可能需要比分布式应用程序中的任何模块都需要的功能更高的硬件。</span><span class="sxs-lookup"><span data-stu-id="cf991-118">This may require higher-capability hardware than any module in a distributed application would need.</span></span> <span data-ttu-id="cf991-119">此外，如果应用程序的任何部分成为瓶颈，则必须将整个应用程序部署到其他计算机节点，以便进行横向扩展。</span><span class="sxs-lookup"><span data-stu-id="cf991-119">Also, if any part of the app becomes a bottleneck, the entire application must be deployed to additional machine nodes in order to scale out.</span></span>

### <a name="environment"></a><span data-ttu-id="cf991-120">环境</span><span class="sxs-lookup"><span data-stu-id="cf991-120">Environment</span></span>

<span data-ttu-id="cf991-121">整体应用程序通常部署在现有宿主环境（操作系统、安装的框架等）中。</span><span class="sxs-lookup"><span data-stu-id="cf991-121">Monolithic applications are typically deployed into an existing hosting environment (operating system, installed frameworks, etc.).</span></span> <span data-ttu-id="cf991-122">此环境可能与应用程序的开发或测试环境不匹配。</span><span class="sxs-lookup"><span data-stu-id="cf991-122">This environment may not match the environment in which the application was developed or tested.</span></span> <span data-ttu-id="cf991-123">应用程序环境中的不一致是单一部署问题的常见根源。</span><span class="sxs-lookup"><span data-stu-id="cf991-123">Inconsistencies in the application's environment are a common source of problems for monolithic deployments.</span></span>

### <a name="coupling"></a><span data-ttu-id="cf991-124">耦合</span><span class="sxs-lookup"><span data-stu-id="cf991-124">Coupling</span></span>

<span data-ttu-id="cf991-125">在应用程序的不同部分之间以及应用程序及其环境之间，单一应用程序可能有很大的耦合。</span><span class="sxs-lookup"><span data-stu-id="cf991-125">Monolithic applications are likely to have a great deal of coupling between different parts of the application, and between the application and its environment.</span></span> <span data-ttu-id="cf991-126">这可能会导致难以确定特定服务或其他问题，以便提高其可伸缩性或替换为替代实现。</span><span class="sxs-lookup"><span data-stu-id="cf991-126">This can make it difficult to factor out a particular service or concern later, in order to increase its scalability or swap in an alternative implementation.</span></span> <span data-ttu-id="cf991-127">此耦合还会导致对系统的更改产生更大的潜在影响，在较大的应用程序中需要大量测试。</span><span class="sxs-lookup"><span data-stu-id="cf991-127">This coupling also leads to much larger potential impacts for changes to the system, requiring extensive testing in larger applications.</span></span>

### <a name="technology-choice"></a><span data-ttu-id="cf991-128">技术选择</span><span class="sxs-lookup"><span data-stu-id="cf991-128">Technology choice</span></span>

<span data-ttu-id="cf991-129">整体应用程序作为一个单元进行生成和部署。</span><span class="sxs-lookup"><span data-stu-id="cf991-129">Monolithic applications are built and deployed as a unit.</span></span> <span data-ttu-id="cf991-130">这提供了简易性和一致性，但可能是创新的障碍。</span><span class="sxs-lookup"><span data-stu-id="cf991-130">This offers simplicity and uniformity but can be a barrier to innovation.</span></span> <span data-ttu-id="cf991-131">尽管系统中的新功能或模块可能更适合于更现代的平台或框架，但很可能是使用应用程序的当前方法构建的，目的是为了实现一致性以及轻松开发和部署。</span><span class="sxs-lookup"><span data-stu-id="cf991-131">Although a new feature or module in the system might be better-suited to a more modern platform or framework, it's likely to be built using the application's current approach for the sake of consistency as well as ease of development and deployment.</span></span>

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a><span data-ttu-id="cf991-132">容器和协调器的好处是什么？</span><span class="sxs-lookup"><span data-stu-id="cf991-132">What are the benefits of containers and orchestrators?</span></span>

<span data-ttu-id="cf991-133">Docker 是最流行的容器管理和映像平台，可让你快速地在 Linux 和 Windows 上使用容器。</span><span class="sxs-lookup"><span data-stu-id="cf991-133">Docker is the most popular container management and imaging platform and allows you to quickly work with containers on Linux and Windows.</span></span> <span data-ttu-id="cf991-134">容器提供独立但可重复的应用程序环境，这些环境在任何系统上以相同的方式运行。</span><span class="sxs-lookup"><span data-stu-id="cf991-134">Containers provide separate but reproducible application environments that run the same way on any system.</span></span> <span data-ttu-id="cf991-135">这使它们非常适合于在云本机应用程序中开发和承载应用程序和应用程序组件。</span><span class="sxs-lookup"><span data-stu-id="cf991-135">This makes them perfect for developing and hosting applications and app components in cloud-native applications.</span></span> <span data-ttu-id="cf991-136">容器彼此隔离，因此同一主机硬件上的两个容器可以安装不同版本的软件，甚至还可以安装操作系统，而不会导致冲突。</span><span class="sxs-lookup"><span data-stu-id="cf991-136">Containers are isolated from one another, so two containers on the same host hardware can have different versions of software and even operating system installed, without the dependencies causing conflicts.</span></span>

<span data-ttu-id="cf991-137">而且，容器是通过可签入源代码管理的简单文件定义的。</span><span class="sxs-lookup"><span data-stu-id="cf991-137">What’s more, containers are defined by simple files that can be checked into source control.</span></span> <span data-ttu-id="cf991-138">与完整服务器（甚至是虚拟机）不同，通常情况下需要手动工作来应用更新或安装其他服务，容器基础结构很容易受版本控制。</span><span class="sxs-lookup"><span data-stu-id="cf991-138">Unlike full servers, even virtual machines, which frequently require manual work to apply updates or install additional services, container infrastructure can easily be version-controlled.</span></span> <span data-ttu-id="cf991-139">因此，可使用自动工具作为生成管道的一部分来开发、测试和部署在容器中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="cf991-139">Thus, apps built to run in containers can be developed, tested, and deployed using automated tools as part of a build pipeline.</span></span>

<span data-ttu-id="cf991-140">容器是不可变的。</span><span class="sxs-lookup"><span data-stu-id="cf991-140">Containers are immutable.</span></span> <span data-ttu-id="cf991-141">获得容器的定义后，你可以重新创建该容器，并且它将以完全相同的方式运行。</span><span class="sxs-lookup"><span data-stu-id="cf991-141">Once you have the definition of a container, you can recreate that container and it will run exactly the same way.</span></span> <span data-ttu-id="cf991-142">这种不可变性适用于基于组件的设计。</span><span class="sxs-lookup"><span data-stu-id="cf991-142">This immutability lends itself to component-based design.</span></span> <span data-ttu-id="cf991-143">如果应用程序的某些部分不会像其他部分一样频繁更改，那么，当你只是部署最常更改的部件时，为什么要重新部署整个应用？</span><span class="sxs-lookup"><span data-stu-id="cf991-143">If some parts of an application don’t change as often as others, why redeploy the entire app when you can just deploy the parts that change most frequently?</span></span> <span data-ttu-id="cf991-144">应用的不同功能和交叉切削问题可以分解为单独的单位。</span><span class="sxs-lookup"><span data-stu-id="cf991-144">Different features and cross-cutting concerns of an app can be broken up into separate units.</span></span> <span data-ttu-id="cf991-145">图3-2 显示了单一应用程序如何通过委托某些功能来利用容器和微服务。</span><span class="sxs-lookup"><span data-stu-id="cf991-145">Figure 3-2 shows how a monolithic app can take advantage of containers and microservices by delegating certain features or functionality.</span></span> <span data-ttu-id="cf991-146">应用程序本身中的其余功能也已容器化。</span><span class="sxs-lookup"><span data-stu-id="cf991-146">The remaining functionality in the app itself has also been containerized.</span></span>

<span data-ttu-id="cf991-147">![打破单一应用程序，以便在后端使用微服务。](./media/breaking-up-monolith-with-backend-microservices.png)
**图 3-2**。</span><span class="sxs-lookup"><span data-stu-id="cf991-147">![Breaking up a monolithic app to use microservices in the back end.](./media/breaking-up-monolith-with-backend-microservices.png)
**Figure 3-2**.</span></span> <span data-ttu-id="cf991-148">分解单一应用程序以在后端使用微服务。</span><span class="sxs-lookup"><span data-stu-id="cf991-148">Breaking up a monolithic app to use microservices in the back end.</span></span>

<span data-ttu-id="cf991-149">使用单独容器构建的云本机应用会受益于根据需要部署尽可能多或更少的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf991-149">Cloud-native apps built using separate containers benefit from the ability to deploy as much or as little of an application as needed.</span></span> <span data-ttu-id="cf991-150">可以在节点上托管单个服务，每个服务都有相应的资源。</span><span class="sxs-lookup"><span data-stu-id="cf991-150">Individual services can be hosted on nodes with resources appropriate to each service.</span></span> <span data-ttu-id="cf991-151">每个服务的运行环境是不可变的，可以在开发、测试和生产之间共享，并且可以轻松地进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="cf991-151">The environment each service runs in is immutable, can be shared between dev, test, and production, and can easily be versioned.</span></span> <span data-ttu-id="cf991-152">应用程序的不同区域之间的耦合与服务间的调用或消息（而不是单体架构中的编译时依赖关系）显式发生。</span><span class="sxs-lookup"><span data-stu-id="cf991-152">Coupling between different areas of the application occurs explicitly as calls or messages between services, not compile-time dependencies within the monolith.</span></span> <span data-ttu-id="cf991-153">整个应用程序的任何给定部分都可以选择对该功能或功能最有效的技术，无需更改应用程序的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cf991-153">And any given part of the overall app can choose the technology that makes the most sense for that feature or capability without requiring changes to the rest of the app.</span></span>

## <a name="what-are-the-scaling-benefits"></a><span data-ttu-id="cf991-154">缩放的优点是什么？</span><span class="sxs-lookup"><span data-stu-id="cf991-154">What are the scaling benefits?</span></span>

<span data-ttu-id="cf991-155">基于容器构建的服务可以利用 Kubernetes 等业务流程工具提供的缩放权益。</span><span class="sxs-lookup"><span data-stu-id="cf991-155">Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes.</span></span> <span data-ttu-id="cf991-156">设计容器仅知道自己的情况。</span><span class="sxs-lookup"><span data-stu-id="cf991-156">By design containers only know about themselves.</span></span> <span data-ttu-id="cf991-157">一旦开始使用多个需要协同工作的容器，就可以在更高的级别对其进行组织。</span><span class="sxs-lookup"><span data-stu-id="cf991-157">Once you start to have multiple containers that need to work together, it can be worthwhile to organize them at a higher level.</span></span> <span data-ttu-id="cf991-158">组织大量的容器及其共享依赖项（如网络配置）是业务流程工具在其中节省时间的地方！</span><span class="sxs-lookup"><span data-stu-id="cf991-158">Organizing large numbers of containers and their shared dependencies, such as network configuration, is where orchestration tools come in to save the day!</span></span> <span data-ttu-id="cf991-159">Kubernetes 是一个容器业务流程平台，旨在自动部署、缩放和管理容器化应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf991-159">Kubernetes is a container orchestration platform designed to automate deployment, scaling, and management of containerized applications.</span></span> <span data-ttu-id="cf991-160">它在容器组的顶层创建一个抽象层，然后将它们组织到*pod。*</span><span class="sxs-lookup"><span data-stu-id="cf991-160">It creates an abstraction layer on top of groups of containers and organizes them into *pods*.</span></span> <span data-ttu-id="cf991-161">Pod 在称为*节点*的辅助角色计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="cf991-161">Pods run on worker machines referred to as *nodes*.</span></span> <span data-ttu-id="cf991-162">整个组织组称为*群集*。</span><span class="sxs-lookup"><span data-stu-id="cf991-162">The whole organized group is referred to as a *cluster*.</span></span> <span data-ttu-id="cf991-163">图3-3 显示了 Kubernetes 群集的不同组件。</span><span class="sxs-lookup"><span data-stu-id="cf991-163">Figure 3-3 shows the different components of a Kubernetes cluster.</span></span>

<span data-ttu-id="cf991-164">![Kubernetes 群集组件。](./media/kubernetes-cluster-components.png)
**图 3-3**。</span><span class="sxs-lookup"><span data-stu-id="cf991-164">![Kubernetes cluster components.](./media/kubernetes-cluster-components.png)
**Figure 3-3**.</span></span> <span data-ttu-id="cf991-165">Kubernetes 群集组件。</span><span class="sxs-lookup"><span data-stu-id="cf991-165">Kubernetes cluster components.</span></span>

<span data-ttu-id="cf991-166">Kubernetes 为满足需求的缩放群集提供内置支持。</span><span class="sxs-lookup"><span data-stu-id="cf991-166">Kubernetes has built-in support for scaling clusters to meet demand.</span></span> <span data-ttu-id="cf991-167">与容器化微服务相结合，这提供了云本机应用程序，能够在需要时以及在需要时利用其他资源快速有效地响应高峰需求。</span><span class="sxs-lookup"><span data-stu-id="cf991-167">Combined with containerized micro-services, this provides cloud-native applications with the ability to quickly and efficiently respond to spikes in demand with additional resources when and where they're needed.</span></span>

### <a name="declarative-versus-imperative"></a><span data-ttu-id="cf991-168">声明性与命令式</span><span class="sxs-lookup"><span data-stu-id="cf991-168">Declarative versus imperative</span></span>

<span data-ttu-id="cf991-169">Kubernetes 支持声明性和命令性对象配置。</span><span class="sxs-lookup"><span data-stu-id="cf991-169">Kubernetes supports both declarative and imperative object configuration.</span></span> <span data-ttu-id="cf991-170">命令式方法涉及运行各种命令，这些命令告诉 Kubernetes 如何执行每个步骤。</span><span class="sxs-lookup"><span data-stu-id="cf991-170">The imperative approach involves running various commands that tell Kubernetes what to do each step of the way.</span></span> <span data-ttu-id="cf991-171">*运行*此映像。</span><span class="sxs-lookup"><span data-stu-id="cf991-171">*Run* this image.</span></span> <span data-ttu-id="cf991-172">*删除*此 pod。</span><span class="sxs-lookup"><span data-stu-id="cf991-172">*Delete* this pod.</span></span> <span data-ttu-id="cf991-173">*公开*此端口。</span><span class="sxs-lookup"><span data-stu-id="cf991-173">*Expose* this port.</span></span> <span data-ttu-id="cf991-174">使用声明性方法，你可以使用描述*所需内容*的配置文件，而不是*执行哪些操作*并 Kubernetes 的内容来了解如何实现所需的结束状态。</span><span class="sxs-lookup"><span data-stu-id="cf991-174">With the declarative approach, you use a configuration file that describes *what you want* instead of *what to do* and Kubernetes figures out what to do to achieve the desired end state.</span></span> <span data-ttu-id="cf991-175">如果已使用命令性命令配置了群集，则可以使用 `kubectl get svc SERVICENAME -o yaml > service.yaml`导出声明性清单。</span><span class="sxs-lookup"><span data-stu-id="cf991-175">If you've already configured your cluster using imperative commands, you can export a declarative manifest by using `kubectl get svc SERVICENAME -o yaml > service.yaml`.</span></span> <span data-ttu-id="cf991-176">这将生成如下清单文件：</span><span class="sxs-lookup"><span data-stu-id="cf991-176">This will produce a manifest file like this one:</span></span>

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

<span data-ttu-id="cf991-177">使用声明性配置时，你可以预览将在提交之前所做的更改，方法是对配置文件所在的文件夹使用 `kubectl diff -f FOLDERNAME`。</span><span class="sxs-lookup"><span data-stu-id="cf991-177">When using declarative configuration, you can preview the changes that will be made before committing them by using `kubectl diff -f FOLDERNAME` against the folder where your configuration files are located.</span></span> <span data-ttu-id="cf991-178">确定要应用这些更改后，请运行 `kubectl apply -f FOLDERNAME`。</span><span class="sxs-lookup"><span data-stu-id="cf991-178">Once you're sure you want to apply the changes, run `kubectl apply -f FOLDERNAME`.</span></span> <span data-ttu-id="cf991-179">添加 `-R` 以递归方式处理文件夹层次结构。</span><span class="sxs-lookup"><span data-stu-id="cf991-179">Add `-R` to recursively process a folder hierarchy.</span></span>

<span data-ttu-id="cf991-180">除了服务之外，还可以对其他 Kubernetes 功能（例如*部署*）使用声明性配置。</span><span class="sxs-lookup"><span data-stu-id="cf991-180">In addition to services, you can use declarative configuration for other Kubernetes features, such as *deployments*.</span></span> <span data-ttu-id="cf991-181">部署控制器使用声明性部署来更新群集资源。</span><span class="sxs-lookup"><span data-stu-id="cf991-181">Declarative deployments are used by deployment controllers to update cluster resources.</span></span> <span data-ttu-id="cf991-182">部署用于推出新的更改，增加以支持更多负载，或回滚到以前的修订版本。</span><span class="sxs-lookup"><span data-stu-id="cf991-182">Deployments are used to roll out new changes, scale up to support more load, or roll back to a previous revision.</span></span> <span data-ttu-id="cf991-183">如果群集不稳定，则声明性部署提供一种机制，用于自动将群集恢复到所需状态。</span><span class="sxs-lookup"><span data-stu-id="cf991-183">If a cluster is unstable, declarative deployments provide a mechanism for automatically bringing the cluster back to a desired state.</span></span>

<span data-ttu-id="cf991-184">使用声明性配置，可将基础结构表示为可签入并在应用程序代码中进行版本控制的代码。</span><span class="sxs-lookup"><span data-stu-id="cf991-184">Using declarative configuration allows infrastructure to be represented as code that can be checked in and versioned alongside the application code.</span></span> <span data-ttu-id="cf991-185">这为使用绑定到源代码管理更改的生成和部署管道提供了改进的更改控制和更好的支持。</span><span class="sxs-lookup"><span data-stu-id="cf991-185">This provides improved change control and better support for continuous deployment using a build and deploy pipeline tied to source control changes.</span></span>

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a><span data-ttu-id="cf991-186">哪些方案适用于容器和协调器？</span><span class="sxs-lookup"><span data-stu-id="cf991-186">What scenarios are ideal for containers and orchestrators?</span></span>

<span data-ttu-id="cf991-187">以下方案非常适合使用容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="cf991-187">The following scenarios are ideal for using containers and orchestrators.</span></span>

### <a name="applications-requiring-high-uptime-and-scalability"></a><span data-ttu-id="cf991-188">需要高运行时间和可伸缩性的应用程序</span><span class="sxs-lookup"><span data-stu-id="cf991-188">Applications requiring high uptime and scalability</span></span>

<span data-ttu-id="cf991-189">具有高运行时间和伸缩性要求的单个应用程序是使用微服务、容器和协调器的云本机体系结构的理想选择。</span><span class="sxs-lookup"><span data-stu-id="cf991-189">Individual applications that have high uptime and scalability requirements are ideal candidates for cloud-native architectures using microservices, containers, and orchestrators.</span></span> <span data-ttu-id="cf991-190">可以在使用版本控制环境的容器中开发这些应用程序，可以在投入生产之前对其进行广泛的测试，并可以在不停机的情况下部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="cf991-190">These applications can be developed in containers using versioned environments, can be extensively tested before going to production, and can be deployed to production with zero downtime.</span></span> <span data-ttu-id="cf991-191">使用 Kubernetes 群集可确保这样的应用程序也可以按需缩放，并从节点故障中自动恢复。</span><span class="sxs-lookup"><span data-stu-id="cf991-191">The use of Kubernetes clusters ensures such apps can also scale on demand and recover automatically from node failures.</span></span>

### <a name="large-numbers-of-applications"></a><span data-ttu-id="cf991-192">大量应用程序</span><span class="sxs-lookup"><span data-stu-id="cf991-192">Large numbers of applications</span></span>

<span data-ttu-id="cf991-193">部署和必须随后维护大量应用程序的组织可从容器和协调器中获益。</span><span class="sxs-lookup"><span data-stu-id="cf991-193">Organizations that deploy and must subsequently maintain large numbers of applications benefit from containers and orchestrators.</span></span> <span data-ttu-id="cf991-194">设置容器化环境和 Kubernetes 群集的前期工作主要是一项固定成本。</span><span class="sxs-lookup"><span data-stu-id="cf991-194">The up front effort of setting up containerized environments and Kubernetes clusters is primarily a fixed cost.</span></span> <span data-ttu-id="cf991-195">部署、维护和更新单个应用程序的成本与必须维护的应用程序的数量不同。</span><span class="sxs-lookup"><span data-stu-id="cf991-195">Deploying, maintaining, and updating individual applications has a cost that varies with the number of applications that must be maintained.</span></span> <span data-ttu-id="cf991-196">除了一定数量的应用程序之外，手动维护自定义应用程序的复杂性超出了使用容器和协调器实现解决方案的成本。</span><span class="sxs-lookup"><span data-stu-id="cf991-196">Beyond a certain fairly small number of applications, the complexity of maintaining custom applications manually exceeds the cost of implementing a solution using containers and orchestrators.</span></span>

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a><span data-ttu-id="cf991-197">何时应避免使用容器和协调器？</span><span class="sxs-lookup"><span data-stu-id="cf991-197">When should you avoid using containers and orchestrators?</span></span>

<span data-ttu-id="cf991-198">如果你不愿意或无法按照十二因素应用程序原则构建应用程序，则可能会更好地避免容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="cf991-198">If you're unwilling or unable to build your application following Twelve-Factor App principles, you'll probably be better off avoiding containers and orchestrators.</span></span> <span data-ttu-id="cf991-199">在这种情况下，最好前进到基于 VM 的托管平台，或者可能是某个混合系统，你可以在其中将某些功能关闭为单独的容器，甚至无服务器功能。</span><span class="sxs-lookup"><span data-stu-id="cf991-199">In these cases, it may be best to move forward with a VM-based hosting platform, or possibly some hybrid system in which you can spin off certain pieces of functionality into separate containers or even serverless functions.</span></span>

## <a name="development-resources"></a><span data-ttu-id="cf991-200">开发资源</span><span class="sxs-lookup"><span data-stu-id="cf991-200">Development resources</span></span>

<span data-ttu-id="cf991-201">本部分显示了可帮助你开始使用容器和协调器作为下一个应用程序的开发资源的简短列表。</span><span class="sxs-lookup"><span data-stu-id="cf991-201">This section shows a short list of development resources that may help you get started using containers and orchestrators for your next application.</span></span> <span data-ttu-id="cf991-202">如果正在寻找有关如何设计云本机微服务体系结构应用的指南，请阅读此书籍的随附 .net[微服务：容器化 .Net 应用程序的体系结构](https://aka.ms/microservicesebook)。</span><span class="sxs-lookup"><span data-stu-id="cf991-202">If you're looking for guidance on how to design your cloud-native microservices architecture app, read this book's companion, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).</span></span>

### <a name="local-kubernetes-development"></a><span data-ttu-id="cf991-203">本地 Kubernetes 开发</span><span class="sxs-lookup"><span data-stu-id="cf991-203">Local Kubernetes Development</span></span>

<span data-ttu-id="cf991-204">Kubernetes 部署在生产环境中提供了极大价值，但你也可以在本地运行它们。</span><span class="sxs-lookup"><span data-stu-id="cf991-204">Kubernetes deployments provide great value in production environments, but you can also run them locally.</span></span> <span data-ttu-id="cf991-205">尽管很多时候都能独立处理单独的应用程序或微服务，但有时最好能够在本地运行整个系统，就像部署到生产环境时运行的完全一样。</span><span class="sxs-lookup"><span data-stu-id="cf991-205">Although much of the time it's good to be able to work on individual apps or microservices independently, sometimes it's good to be able to run the whole system locally just as it will run when deployed to production.</span></span> <span data-ttu-id="cf991-206">有多种方法可实现此目的，其中两个是 Minikube 和 Docker 桌面。</span><span class="sxs-lookup"><span data-stu-id="cf991-206">There are several ways to achieve this, two of which are Minikube and Docker Desktop.</span></span> <span data-ttu-id="cf991-207">Visual Studio 还提供了用于 Docker 开发的工具。</span><span class="sxs-lookup"><span data-stu-id="cf991-207">Visual Studio also provides tooling for Docker development.</span></span>

### <a name="minikube"></a><span data-ttu-id="cf991-208">Minikube</span><span class="sxs-lookup"><span data-stu-id="cf991-208">Minikube</span></span>

<span data-ttu-id="cf991-209">什么是 Minikube？</span><span class="sxs-lookup"><span data-stu-id="cf991-209">What is Minikube?</span></span> <span data-ttu-id="cf991-210">Minikube 项目显示 "Minikube 在 macOS、Linux 和 Windows 上实现本地 Kubernetes 群集"。</span><span class="sxs-lookup"><span data-stu-id="cf991-210">The Minikube project says "Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows."</span></span> <span data-ttu-id="cf991-211">它的主要目标是 "成为本地 Kubernetes 应用程序开发的最佳工具，并支持所有适合的 Kubernetes 功能"。</span><span class="sxs-lookup"><span data-stu-id="cf991-211">Its primary goals are "to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit."</span></span> <span data-ttu-id="cf991-212">安装 Minikube 与 Docker 分离，但 Minikube 支持不同于 Docker Desktop 支持的虚拟机监控程序。</span><span class="sxs-lookup"><span data-stu-id="cf991-212">Installing Minikube is separate from Docker, but Minikube supports different hypervisors than Docker Desktop supports.</span></span> <span data-ttu-id="cf991-213">Minikube 目前支持以下 Kubernetes 功能：</span><span class="sxs-lookup"><span data-stu-id="cf991-213">The following Kubernetes features are currently supported by Minikube:</span></span>

- <span data-ttu-id="cf991-214">DNS</span><span class="sxs-lookup"><span data-stu-id="cf991-214">DNS</span></span>
- <span data-ttu-id="cf991-215">NodePorts</span><span class="sxs-lookup"><span data-stu-id="cf991-215">NodePorts</span></span>
- <span data-ttu-id="cf991-216">ConfigMaps 和机密</span><span class="sxs-lookup"><span data-stu-id="cf991-216">ConfigMaps and secrets</span></span>
- <span data-ttu-id="cf991-217">仪表板</span><span class="sxs-lookup"><span data-stu-id="cf991-217">Dashboards</span></span>
- <span data-ttu-id="cf991-218">容器运行时： Docker、rkt、CRI 和 containerd</span><span class="sxs-lookup"><span data-stu-id="cf991-218">Container runtimes: Docker, rkt, CRI-O, and containerd</span></span>
- <span data-ttu-id="cf991-219">启用容器网络接口（CNI）</span><span class="sxs-lookup"><span data-stu-id="cf991-219">Enabling Container Network Interface (CNI)</span></span>
- <span data-ttu-id="cf991-220">传入</span><span class="sxs-lookup"><span data-stu-id="cf991-220">Ingress</span></span>

<span data-ttu-id="cf991-221">安装 Minikube 后，可以通过运行 `minikube start` 命令快速开始使用它，该命令会下载映像并启动本地 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="cf991-221">After installing Minikube, you can quickly start using it by running the `minikube start` command, which downloads an image and start the local Kubernetes cluster.</span></span> <span data-ttu-id="cf991-222">启动群集后，使用标准的 Kubernetes `kubectl` 命令与该群集进行交互。</span><span class="sxs-lookup"><span data-stu-id="cf991-222">Once the cluster is started, you interact with it using the standard Kubernetes `kubectl` commands.</span></span>

### <a name="docker-desktop"></a><span data-ttu-id="cf991-223">Docker 桌面</span><span class="sxs-lookup"><span data-stu-id="cf991-223">Docker Desktop</span></span>

<span data-ttu-id="cf991-224">你还可以直接从 Windows 上的 Docker Desktop 使用 Kubernetes。</span><span class="sxs-lookup"><span data-stu-id="cf991-224">You can also work with Kubernetes directly from Docker Desktop on Windows.</span></span> <span data-ttu-id="cf991-225">如果你使用的是 Windows 容器，则这是你的唯一选择，对于非 Windows 容器也是不错的选择。</span><span class="sxs-lookup"><span data-stu-id="cf991-225">This is your only option if you're using Windows Containers, and is a great choice for non-Windows containers as well.</span></span> <span data-ttu-id="cf991-226">标准 Docker 桌面配置应用用于配置从 Docker Desktop 运行的 Kubernetes。</span><span class="sxs-lookup"><span data-stu-id="cf991-226">The standard Docker Desktop configuration app is used to configure Kubernetes running from Docker Desktop.</span></span>

![在 Docker Desktop 中配置 Kubernetes](./media/docker-desktop-kubernetes.png)

<span data-ttu-id="cf991-228">**图 3-4**。</span><span class="sxs-lookup"><span data-stu-id="cf991-228">**Figure 3-4**.</span></span> <span data-ttu-id="cf991-229">在 Docker Desktop 中配置 Kubernetes。</span><span class="sxs-lookup"><span data-stu-id="cf991-229">Configuring Kubernetes in Docker Desktop.</span></span>

<span data-ttu-id="cf991-230">Docker Desktop 已经是用于本地配置和运行容器化应用程序的最受欢迎的工具。</span><span class="sxs-lookup"><span data-stu-id="cf991-230">Docker Desktop is already the most popular tool for configuring and running containerized apps locally.</span></span> <span data-ttu-id="cf991-231">使用 Docker Desktop 时，可以针对将部署到生产环境中的一组 Docker 容器映像进行本地开发。</span><span class="sxs-lookup"><span data-stu-id="cf991-231">When you work with Docker Desktop, you can develop locally against the exact same set of Docker container images that you'll deploy to production.</span></span> <span data-ttu-id="cf991-232">Docker Desktop 设计为在本地生成、测试和交付容器化应用。</span><span class="sxs-lookup"><span data-stu-id="cf991-232">Docker Desktop is designed to "build, test, and ship" containerized apps locally.</span></span> <span data-ttu-id="cf991-233">将映像发送到映像注册表（如 Azure 容器注册表或 Docker 中心）后，Azure Kubernetes Service （AKS）等服务将在生产环境中管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf991-233">Once the images have been shipped to an image registry like Azure Container Registry or Docker Hub, then services like Azure Kubernetes Service (AKS) manage the application in production.</span></span>

### <a name="visual-studio-docker-tooling"></a><span data-ttu-id="cf991-234">Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="cf991-234">Visual Studio Docker Tooling</span></span>

<span data-ttu-id="cf991-235">Visual Studio 支持对 web 应用程序进行 Docker 开发。</span><span class="sxs-lookup"><span data-stu-id="cf991-235">Visual Studio supports Docker development for web applications.</span></span> <span data-ttu-id="cf991-236">创建新的 ASP.NET Core 应用程序时，可以选择在项目创建过程中将其配置为 Docker 支持，如图3-5 所示。</span><span class="sxs-lookup"><span data-stu-id="cf991-236">When you create a new ASP.NET Core application, you're given the option to configure it with Docker support as part of the project creation process, as shown in Figure 3-5.</span></span>

![Visual Studio 启用 Docker 支持](./media/visual-studio-enable-docker-support.png)

<span data-ttu-id="cf991-238">**图 3-5**。</span><span class="sxs-lookup"><span data-stu-id="cf991-238">**Figure 3-5**.</span></span> <span data-ttu-id="cf991-239">Visual Studio 启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="cf991-239">Visual Studio Enable Docker Support</span></span>

<span data-ttu-id="cf991-240">如果选择此选项，则将使用其根中的 `Dockerfile` 创建项目，该项目可用于在 Docker 容器中生成和托管应用。</span><span class="sxs-lookup"><span data-stu-id="cf991-240">When this option is selected, the project is created with a `Dockerfile` in its root, which can be used to build and host the app in a Docker container.</span></span> <span data-ttu-id="cf991-241">图3-6 显示了一个示例 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="cf991-241">An example Dockerfile is shown in Figure 3-6.</span></span>

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

<span data-ttu-id="cf991-242">**图 3-6**。</span><span class="sxs-lookup"><span data-stu-id="cf991-242">**Figure 3-6**.</span></span> <span data-ttu-id="cf991-243">Visual Studio 生成的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="cf991-243">Visual Studio generated Dockerfile</span></span>

<span data-ttu-id="cf991-244">应用运行时的默认行为也配置为使用 Docker。</span><span class="sxs-lookup"><span data-stu-id="cf991-244">The default behavior when the app runs is configured to use Docker as well.</span></span> <span data-ttu-id="cf991-245">图3-7 显示了在添加 Docker 支持创建的新 ASP.NET Core 项目中可用的不同运行选项。</span><span class="sxs-lookup"><span data-stu-id="cf991-245">Figure 3-7 shows the different run options available from a new ASP.NET Core project created with Docker support added.</span></span>

![Visual Studio Docker 运行选项](./media/visual-studio-docker-run-options.png)

<span data-ttu-id="cf991-247">**图 3-7**。</span><span class="sxs-lookup"><span data-stu-id="cf991-247">**Figure 3-7**.</span></span> <span data-ttu-id="cf991-248">Visual Studio Docker 运行选项</span><span class="sxs-lookup"><span data-stu-id="cf991-248">Visual Studio Docker Run Options</span></span>

<span data-ttu-id="cf991-249">除了本地开发外， [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/)为多个开发人员提供了一种方便的方法，以便在 Azure 中使用自己的 Kubernetes 配置。</span><span class="sxs-lookup"><span data-stu-id="cf991-249">In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way for multiple developers to work with their own Kubernetes configurations within Azure.</span></span> <span data-ttu-id="cf991-250">如图3-7 所示，还可以在 Azure Dev Spaces 中运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf991-250">As you can see in Figure 3-7, you can also run the application in Azure Dev Spaces.</span></span>

<span data-ttu-id="cf991-251">如果你在创建 ASP.NET Core 应用程序时未将 Docker 支持添加到该应用程序，则可以在以后随时添加它。</span><span class="sxs-lookup"><span data-stu-id="cf991-251">If you don't add Docker support to your ASP.NET Core application when you create it, you can always add it later.</span></span> <span data-ttu-id="cf991-252">在 Visual Studio 解决方案资源管理器中，右键单击项目并选择 "**添加** > **Docker 支持**"，如图3-8 所示。</span><span class="sxs-lookup"><span data-stu-id="cf991-252">From the Visual Studio Solution Explorer, right click on the project and select **Add** > **Docker Support**, as shown in Figure 3-8.</span></span>

![Visual Studio 添加 Docker 支持](./media/visual-studio-add-docker-support.png)

<span data-ttu-id="cf991-254">**图 3-8**。</span><span class="sxs-lookup"><span data-stu-id="cf991-254">**Figure 3-8**.</span></span> <span data-ttu-id="cf991-255">Visual Studio 添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="cf991-255">Visual Studio Add Docker Support</span></span>

<span data-ttu-id="cf991-256">除了 Docker 支持外，还可以添加容器业务流程支持，如图3-8 所示。</span><span class="sxs-lookup"><span data-stu-id="cf991-256">In addition to Docker support, you can also add Container Orchestration Support, also shown in Figure 3-8.</span></span> <span data-ttu-id="cf991-257">默认情况下，orchestrator 将使用 Kubernetes 和 Helm。</span><span class="sxs-lookup"><span data-stu-id="cf991-257">By default, the orchestrator uses Kubernetes and Helm.</span></span> <span data-ttu-id="cf991-258">选择 orchestrator 后，会将一个 `azds.yaml` 文件添加到项目根目录中，并添加一个 `charts` 文件夹，其中包含用于配置应用程序并将其部署到 Kubernetes 的 Helm 图表。</span><span class="sxs-lookup"><span data-stu-id="cf991-258">Once you've chosen the orchestrator, a `azds.yaml` file is added to the project root and a `charts` folder is added containing the Helm charts used to configure and deploy the application to Kubernetes.</span></span> <span data-ttu-id="cf991-259">图3-9 显示新项目中生成的文件。</span><span class="sxs-lookup"><span data-stu-id="cf991-259">Figure 3-9 shows the resulting files in a new project.</span></span>

![Visual Studio 添加 Orchestrator 支持](./media/visual-studio-add-orchestrator-support.png)

<span data-ttu-id="cf991-261">**图 3-9**。</span><span class="sxs-lookup"><span data-stu-id="cf991-261">**Figure 3-9**.</span></span> <span data-ttu-id="cf991-262">Visual Studio 添加 Orchestrator 支持</span><span class="sxs-lookup"><span data-stu-id="cf991-262">Visual Studio Add Orchestrator Support</span></span>

## <a name="references"></a><span data-ttu-id="cf991-263">参考</span><span class="sxs-lookup"><span data-stu-id="cf991-263">References</span></span>

- [<span data-ttu-id="cf991-264">什么是 Kubernetes？</span><span class="sxs-lookup"><span data-stu-id="cf991-264">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="cf991-265">通过 Minikube 安装 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="cf991-265">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="cf991-266">MiniKube vs Docker Desktop</span><span class="sxs-lookup"><span data-stu-id="cf991-266">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="cf991-267">Visual Studio Tools for Docker</span><span class="sxs-lookup"><span data-stu-id="cf991-267">Visual Studio Tools for Docker</span></span>](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
><span data-ttu-id="cf991-268">[上一页](scale-applications.md)
>[下一页](leverage-serverless-functions.md)</span><span class="sxs-lookup"><span data-stu-id="cf991-268">[Previous](scale-applications.md)
[Next](leverage-serverless-functions.md)</span></span>
