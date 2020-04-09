---
title: 利用容器和协调器
description: 利用 Azure 中的 Docker 容器和库伯内特协调器
ms.date: 06/30/2019
ms.openlocfilehash: 44b2fff8c9c88717d83e41a421b9817e2cc68135
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989033"
---
# <a name="leveraging-containers-and-orchestrators"></a><span data-ttu-id="535ea-103">利用容器和协调器</span><span class="sxs-lookup"><span data-stu-id="535ea-103">Leveraging containers and orchestrators</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="535ea-104">容器和协调器旨在解决单一部署方法中常见的问题。</span><span class="sxs-lookup"><span data-stu-id="535ea-104">Containers and orchestrators are designed to solve problems common to monolithic deployment approaches.</span></span>

## <a name="challenges-with-monolithic-deployments"></a><span data-ttu-id="535ea-105">整体部署的挑战</span><span class="sxs-lookup"><span data-stu-id="535ea-105">Challenges with monolithic deployments</span></span>

<span data-ttu-id="535ea-106">传统上，大多数应用程序都部署为单个单元。</span><span class="sxs-lookup"><span data-stu-id="535ea-106">Traditionally, most applications have been deployed as a single unit.</span></span> <span data-ttu-id="535ea-107">此类应用程序称为单体。</span><span class="sxs-lookup"><span data-stu-id="535ea-107">Such applications are referred to as a monolith.</span></span> <span data-ttu-id="535ea-108">这种将应用程序部署为单个单元的一般方法，即使它们由多个模块或程序集组成，也称为单片架构，如图 3-1 所示。</span><span class="sxs-lookup"><span data-stu-id="535ea-108">This general approach of deploying applications as single units even if they're composed of multiple modules or assemblies is known as monolithic architecture, as shown in Figure 3-1.</span></span>

![单体架构。](./media/monolithic-architecture.png)

<span data-ttu-id="535ea-110">**图3-1**。</span><span class="sxs-lookup"><span data-stu-id="535ea-110">**Figure 3-1**.</span></span> <span data-ttu-id="535ea-111">单体架构。</span><span class="sxs-lookup"><span data-stu-id="535ea-111">Monolithic architecture.</span></span>

<span data-ttu-id="535ea-112">尽管单片式架构具有简单性的优点，但它们面临着许多挑战：</span><span class="sxs-lookup"><span data-stu-id="535ea-112">Although they have the benefit of simplicity, monolithic architectures face a number of challenges:</span></span>

### <a name="deployments"></a><span data-ttu-id="535ea-113">部署</span><span class="sxs-lookup"><span data-stu-id="535ea-113">Deployments</span></span>

<span data-ttu-id="535ea-114">部署到单一应用程序通常需要重新启动整个应用程序，即使只替换一个小型模块也是如此。</span><span class="sxs-lookup"><span data-stu-id="535ea-114">Deploying to monolithic applications typically requires restarting the entire application, even if only one small module is being replaced.</span></span> <span data-ttu-id="535ea-115">根据托管应用程序的计算机数，这可能导致部署期间的停机时间。</span><span class="sxs-lookup"><span data-stu-id="535ea-115">Depending on the number of machines hosting the application, this can result in downtime during deployments.</span></span>

### <a name="hosting"></a><span data-ttu-id="535ea-116">Hosting</span><span class="sxs-lookup"><span data-stu-id="535ea-116">Hosting</span></span>

<span data-ttu-id="535ea-117">单片应用程序完全托管在单个计算机实例上。</span><span class="sxs-lookup"><span data-stu-id="535ea-117">Monolithic applications are hosted entirely on a single machine instance.</span></span> <span data-ttu-id="535ea-118">这可能需要比分布式应用程序中任何模块所需的更高功能的硬件。</span><span class="sxs-lookup"><span data-stu-id="535ea-118">This may require higher-capability hardware than any module in a distributed application would need.</span></span> <span data-ttu-id="535ea-119">此外，如果应用的任何部分成为瓶颈，则必须将整个应用程序部署到其他计算机节点才能横向扩展。</span><span class="sxs-lookup"><span data-stu-id="535ea-119">Also, if any part of the app becomes a bottleneck, the entire application must be deployed to additional machine nodes in order to scale out.</span></span>

### <a name="environment"></a><span data-ttu-id="535ea-120">环境</span><span class="sxs-lookup"><span data-stu-id="535ea-120">Environment</span></span>

<span data-ttu-id="535ea-121">单片应用程序通常部署到现有的托管环境（操作系统、已安装的框架等）。</span><span class="sxs-lookup"><span data-stu-id="535ea-121">Monolithic applications are typically deployed into an existing hosting environment (operating system, installed frameworks, etc.).</span></span> <span data-ttu-id="535ea-122">此环境可能与开发或测试应用程序的环境不匹配。</span><span class="sxs-lookup"><span data-stu-id="535ea-122">This environment may not match the environment in which the application was developed or tested.</span></span> <span data-ttu-id="535ea-123">应用程序环境中的不一致是单一部署的常见问题来源。</span><span class="sxs-lookup"><span data-stu-id="535ea-123">Inconsistencies in the application's environment are a common source of problems for monolithic deployments.</span></span>

### <a name="coupling"></a><span data-ttu-id="535ea-124">耦合</span><span class="sxs-lookup"><span data-stu-id="535ea-124">Coupling</span></span>

<span data-ttu-id="535ea-125">单片应用程序在应用程序的不同部分之间以及应用程序与其环境之间可能有很大的耦合。</span><span class="sxs-lookup"><span data-stu-id="535ea-125">Monolithic applications are likely to have a great deal of coupling between different parts of the application, and between the application and its environment.</span></span> <span data-ttu-id="535ea-126">这会使以后难以分解特定服务或问题，以便增加其可伸缩性或在替代实现中交换。</span><span class="sxs-lookup"><span data-stu-id="535ea-126">This can make it difficult to factor out a particular service or concern later, in order to increase its scalability or swap in an alternative implementation.</span></span> <span data-ttu-id="535ea-127">这种耦合还会导致对系统更改产生更大的潜在影响，需要在较大的应用中进行广泛的测试。</span><span class="sxs-lookup"><span data-stu-id="535ea-127">This coupling also leads to much larger potential impacts for changes to the system, requiring extensive testing in larger applications.</span></span>

### <a name="technology-choice"></a><span data-ttu-id="535ea-128">技术选择</span><span class="sxs-lookup"><span data-stu-id="535ea-128">Technology choice</span></span>

<span data-ttu-id="535ea-129">单片应用程序作为一个单元构建和部署。</span><span class="sxs-lookup"><span data-stu-id="535ea-129">Monolithic applications are built and deployed as a unit.</span></span> <span data-ttu-id="535ea-130">这提供了简单性和统一性，但可能是创新的障碍。</span><span class="sxs-lookup"><span data-stu-id="535ea-130">This offers simplicity and uniformity but can be a barrier to innovation.</span></span> <span data-ttu-id="535ea-131">尽管系统中的新功能或模块可能更适合更现代的平台或框架，但为了一致性以及易于开发和部署，可能会使用应用程序的当前方法构建它。</span><span class="sxs-lookup"><span data-stu-id="535ea-131">Although a new feature or module in the system might be better-suited to a more modern platform or framework, it's likely to be built using the application's current approach for the sake of consistency as well as ease of development and deployment.</span></span>

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a><span data-ttu-id="535ea-132">容器和协调器有什么好处？</span><span class="sxs-lookup"><span data-stu-id="535ea-132">What are the benefits of containers and orchestrators?</span></span>

<span data-ttu-id="535ea-133">Docker 是最受欢迎的容器管理和映像平台，允许您快速处理 Linux 和 Windows 上的容器。</span><span class="sxs-lookup"><span data-stu-id="535ea-133">Docker is the most popular container management and imaging platform and allows you to quickly work with containers on Linux and Windows.</span></span> <span data-ttu-id="535ea-134">容器提供单独但可重现的应用程序环境，这些环境在任何系统上以相同的方式运行。</span><span class="sxs-lookup"><span data-stu-id="535ea-134">Containers provide separate but reproducible application environments that run the same way on any system.</span></span> <span data-ttu-id="535ea-135">这使得它们非常适合在云原生应用程序中开发和托管应用程序和应用程序组件。</span><span class="sxs-lookup"><span data-stu-id="535ea-135">This makes them perfect for developing and hosting applications and app components in cloud-native applications.</span></span> <span data-ttu-id="535ea-136">容器彼此隔离，因此同一主机硬件上的两个容器可以安装不同版本的软件，甚至操作系统，而不会造成依赖项冲突。</span><span class="sxs-lookup"><span data-stu-id="535ea-136">Containers are isolated from one another, so two containers on the same host hardware can have different versions of software and even operating system installed, without the dependencies causing conflicts.</span></span>

<span data-ttu-id="535ea-137">此外，容器由可签入源代码管理的简单文件定义。</span><span class="sxs-lookup"><span data-stu-id="535ea-137">What's more, containers are defined by simple files that can be checked into source control.</span></span> <span data-ttu-id="535ea-138">与完整服务器（甚至虚拟机）不同，通常需要手动工作才能应用更新或安装其他服务，因此容器基础结构很容易被版本控制。</span><span class="sxs-lookup"><span data-stu-id="535ea-138">Unlike full servers, even virtual machines, which frequently require manual work to apply updates or install additional services, container infrastructure can easily be version-controlled.</span></span> <span data-ttu-id="535ea-139">因此，在容器中运行构建的应用可以使用自动工具作为生成管道的一部分进行开发、测试和部署。</span><span class="sxs-lookup"><span data-stu-id="535ea-139">Thus, apps built to run in containers can be developed, tested, and deployed using automated tools as part of a build pipeline.</span></span>

<span data-ttu-id="535ea-140">容器是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="535ea-140">Containers are immutable.</span></span> <span data-ttu-id="535ea-141">获得容器的定义后，可以重新创建该容器，并且它将以完全相同的方式运行。</span><span class="sxs-lookup"><span data-stu-id="535ea-141">Once you have the definition of a container, you can recreate that container and it will run exactly the same way.</span></span> <span data-ttu-id="535ea-142">这种不变性适用于基于组件的设计。</span><span class="sxs-lookup"><span data-stu-id="535ea-142">This immutability lends itself to component-based design.</span></span> <span data-ttu-id="535ea-143">如果应用程序的某些部分更改频率不如其他部分频繁，那么为什么当您只需部署更改次数最多的部分时，才能重新部署整个应用程序？</span><span class="sxs-lookup"><span data-stu-id="535ea-143">If some parts of an application don't change as often as others, why redeploy the entire app when you can just deploy the parts that change most frequently?</span></span> <span data-ttu-id="535ea-144">应用的不同功能和交叉问题可以分解为单独的单元。</span><span class="sxs-lookup"><span data-stu-id="535ea-144">Different features and cross-cutting concerns of an app can be broken up into separate units.</span></span> <span data-ttu-id="535ea-145">图 3-2 显示了单片应用如何通过委派某些功能或功能来利用容器和微服务。</span><span class="sxs-lookup"><span data-stu-id="535ea-145">Figure 3-2 shows how a monolithic app can take advantage of containers and microservices by delegating certain features or functionality.</span></span> <span data-ttu-id="535ea-146">应用本身的剩余功能也已容器化。</span><span class="sxs-lookup"><span data-stu-id="535ea-146">The remaining functionality in the app itself has also been containerized.</span></span>

<span data-ttu-id="535ea-147">![分解单片应用，在后端使用微服务。](./media/breaking-up-monolith-with-backend-microservices.png)
**图3-2**.</span><span class="sxs-lookup"><span data-stu-id="535ea-147">![Breaking up a monolithic app to use microservices in the back end.](./media/breaking-up-monolith-with-backend-microservices.png)
**Figure 3-2**.</span></span> <span data-ttu-id="535ea-148">分解单片应用，在后端使用微服务。</span><span class="sxs-lookup"><span data-stu-id="535ea-148">Breaking up a monolithic app to use microservices in the back end.</span></span>

<span data-ttu-id="535ea-149">使用单独的容器构建的云原生应用可根据需要部署尽可能多的或很少的应用程序。</span><span class="sxs-lookup"><span data-stu-id="535ea-149">Cloud-native apps built using separate containers benefit from the ability to deploy as much or as little of an application as needed.</span></span> <span data-ttu-id="535ea-150">单个服务可以托管在具有适合每个服务的节点上。</span><span class="sxs-lookup"><span data-stu-id="535ea-150">Individual services can be hosted on nodes with resources appropriate to each service.</span></span> <span data-ttu-id="535ea-151">每个服务运行的环境是不可变的，可以在开发、测试和生产之间共享，并且可以轻松进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="535ea-151">The environment each service runs in is immutable, can be shared between dev, test, and production, and can easily be versioned.</span></span> <span data-ttu-id="535ea-152">应用程序不同区域之间的耦合作为服务之间的调用或消息显式发生，而不是单体中的编译时间依赖项。</span><span class="sxs-lookup"><span data-stu-id="535ea-152">Coupling between different areas of the application occurs explicitly as calls or messages between services, not compile-time dependencies within the monolith.</span></span> <span data-ttu-id="535ea-153">整个应用的任何给定部分都可以选择对该功能或功能最有意义的技术，而无需更改应用的其余部分。</span><span class="sxs-lookup"><span data-stu-id="535ea-153">And any given part of the overall app can choose the technology that makes the most sense for that feature or capability without requiring changes to the rest of the app.</span></span>

## <a name="what-are-the-scaling-benefits"></a><span data-ttu-id="535ea-154">扩展优势是什么？</span><span class="sxs-lookup"><span data-stu-id="535ea-154">What are the scaling benefits?</span></span>

<span data-ttu-id="535ea-155">构建在容器上的服务可以利用库伯奈斯等业务流程工具提供的扩展优势。</span><span class="sxs-lookup"><span data-stu-id="535ea-155">Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes.</span></span> <span data-ttu-id="535ea-156">根据设计，容器只知道自己。</span><span class="sxs-lookup"><span data-stu-id="535ea-156">By design containers only know about themselves.</span></span> <span data-ttu-id="535ea-157">一旦开始有多个容器需要协同工作，就可以在更高的级别组织它们。</span><span class="sxs-lookup"><span data-stu-id="535ea-157">Once you start to have multiple containers that need to work together, it can be worthwhile to organize them at a higher level.</span></span> <span data-ttu-id="535ea-158">组织大量容器及其共享依赖项（如网络配置）是业务流程工具用于节省一天的位置！</span><span class="sxs-lookup"><span data-stu-id="535ea-158">Organizing large numbers of containers and their shared dependencies, such as network configuration, is where orchestration tools come in to save the day!</span></span> <span data-ttu-id="535ea-159">Kubernetes 是一个容器编排平台，旨在自动部署、扩展和管理容器化应用程序。</span><span class="sxs-lookup"><span data-stu-id="535ea-159">Kubernetes is a container orchestration platform designed to automate deployment, scaling, and management of containerized applications.</span></span> <span data-ttu-id="535ea-160">它在容器组之上创建一个抽象层，并将它们组织到*窗格中*。</span><span class="sxs-lookup"><span data-stu-id="535ea-160">It creates an abstraction layer on top of groups of containers and organizes them into *pods*.</span></span> <span data-ttu-id="535ea-161">在称为*节点*的工作计算机上运行的 Pod。</span><span class="sxs-lookup"><span data-stu-id="535ea-161">Pods run on worker machines referred to as *nodes*.</span></span> <span data-ttu-id="535ea-162">整个有组织的组称为*群集*。</span><span class="sxs-lookup"><span data-stu-id="535ea-162">The whole organized group is referred to as a *cluster*.</span></span> <span data-ttu-id="535ea-163">图 3-3 显示了库伯内斯群集的不同组件。</span><span class="sxs-lookup"><span data-stu-id="535ea-163">Figure 3-3 shows the different components of a Kubernetes cluster.</span></span>

<span data-ttu-id="535ea-164">![库伯内斯集群组件。](./media/kubernetes-cluster-components.png)
**图3-3**.</span><span class="sxs-lookup"><span data-stu-id="535ea-164">![Kubernetes cluster components.](./media/kubernetes-cluster-components.png)
**Figure 3-3**.</span></span> <span data-ttu-id="535ea-165">库伯内斯集群组件。</span><span class="sxs-lookup"><span data-stu-id="535ea-165">Kubernetes cluster components.</span></span>

<span data-ttu-id="535ea-166">Kubernetes 内置支持扩展群集以满足需求。</span><span class="sxs-lookup"><span data-stu-id="535ea-166">Kubernetes has built-in support for scaling clusters to meet demand.</span></span> <span data-ttu-id="535ea-167">结合容器化微服务，这为云原生应用程序提供了在需要时和任何地方使用额外资源快速高效地响应需求高峰的能力。</span><span class="sxs-lookup"><span data-stu-id="535ea-167">Combined with containerized micro-services, this provides cloud-native applications with the ability to quickly and efficiently respond to spikes in demand with additional resources when and where they're needed.</span></span>

### <a name="declarative-versus-imperative"></a><span data-ttu-id="535ea-168">声明性与命令性</span><span class="sxs-lookup"><span data-stu-id="535ea-168">Declarative versus imperative</span></span>

<span data-ttu-id="535ea-169">库伯内斯支持声明性对象和命令性对象配置。</span><span class="sxs-lookup"><span data-stu-id="535ea-169">Kubernetes supports both declarative and imperative object configuration.</span></span> <span data-ttu-id="535ea-170">命令性方法涉及运行各种命令，告诉 Kubernetes 如何执行每一步。</span><span class="sxs-lookup"><span data-stu-id="535ea-170">The imperative approach involves running various commands that tell Kubernetes what to do each step of the way.</span></span> <span data-ttu-id="535ea-171">*运行*此映像。</span><span class="sxs-lookup"><span data-stu-id="535ea-171">*Run* this image.</span></span> <span data-ttu-id="535ea-172">*删除*此窗格。</span><span class="sxs-lookup"><span data-stu-id="535ea-172">*Delete* this pod.</span></span> <span data-ttu-id="535ea-173">*公开*此端口。</span><span class="sxs-lookup"><span data-stu-id="535ea-173">*Expose* this port.</span></span> <span data-ttu-id="535ea-174">使用声明性方法，您可以使用一个配置文件来描述*您想要做什么*而不是*做什么*，Kubernetes 会找出要做什么来实现所需的结束状态。</span><span class="sxs-lookup"><span data-stu-id="535ea-174">With the declarative approach, you use a configuration file that describes *what you want* instead of *what to do* and Kubernetes figures out what to do to achieve the desired end state.</span></span> <span data-ttu-id="535ea-175">如果已经使用命令命令配置群集，则可以使用 导出声明性清单`kubectl get svc SERVICENAME -o yaml > service.yaml`。</span><span class="sxs-lookup"><span data-stu-id="535ea-175">If you've already configured your cluster using imperative commands, you can export a declarative manifest by using `kubectl get svc SERVICENAME -o yaml > service.yaml`.</span></span> <span data-ttu-id="535ea-176">这将生成如下所示的清单文件：</span><span class="sxs-lookup"><span data-stu-id="535ea-176">This will produce a manifest file like this one:</span></span>

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

<span data-ttu-id="535ea-177">使用声明性配置时，可以通过对配置文件所在的文件夹进行引用`kubectl diff -f FOLDERNAME`之前预览这些更改。</span><span class="sxs-lookup"><span data-stu-id="535ea-177">When using declarative configuration, you can preview the changes that will be made before committing them by using `kubectl diff -f FOLDERNAME` against the folder where your configuration files are located.</span></span> <span data-ttu-id="535ea-178">确定要应用更改后，请运行`kubectl apply -f FOLDERNAME`。</span><span class="sxs-lookup"><span data-stu-id="535ea-178">Once you're sure you want to apply the changes, run `kubectl apply -f FOLDERNAME`.</span></span> <span data-ttu-id="535ea-179">添加到`-R`递归处理文件夹层次结构。</span><span class="sxs-lookup"><span data-stu-id="535ea-179">Add `-R` to recursively process a folder hierarchy.</span></span>

<span data-ttu-id="535ea-180">除了服务之外，还可以对其他 Kubernetes 功能（如*部署*）使用声明性配置。</span><span class="sxs-lookup"><span data-stu-id="535ea-180">In addition to services, you can use declarative configuration for other Kubernetes features, such as *deployments*.</span></span> <span data-ttu-id="535ea-181">声明性部署由部署控制器用于更新群集资源。</span><span class="sxs-lookup"><span data-stu-id="535ea-181">Declarative deployments are used by deployment controllers to update cluster resources.</span></span> <span data-ttu-id="535ea-182">部署用于添加新更改、向上扩展以支持更多负载或回滚到以前的修订版。</span><span class="sxs-lookup"><span data-stu-id="535ea-182">Deployments are used to roll out new changes, scale up to support more load, or roll back to a previous revision.</span></span> <span data-ttu-id="535ea-183">如果群集不稳定，声明性部署提供了自动将群集恢复到所需状态的机制。</span><span class="sxs-lookup"><span data-stu-id="535ea-183">If a cluster is unstable, declarative deployments provide a mechanism for automatically bringing the cluster back to a desired state.</span></span>

<span data-ttu-id="535ea-184">使用声明性配置可以将基础结构表示为代码，该代码可以签入并随着应用程序代码进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="535ea-184">Using declarative configuration allows infrastructure to be represented as code that can be checked in and versioned alongside the application code.</span></span> <span data-ttu-id="535ea-185">这提供了改进的更改控制，并更好地支持使用与源代码管理更改关联的生成和部署管道进行持续部署。</span><span class="sxs-lookup"><span data-stu-id="535ea-185">This provides improved change control and better support for continuous deployment using a build and deploy pipeline tied to source control changes.</span></span>

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a><span data-ttu-id="535ea-186">哪些方案非常适合容器和协调器？</span><span class="sxs-lookup"><span data-stu-id="535ea-186">What scenarios are ideal for containers and orchestrators?</span></span>

<span data-ttu-id="535ea-187">以下方案非常适合使用容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="535ea-187">The following scenarios are ideal for using containers and orchestrators.</span></span>

### <a name="applications-requiring-high-uptime-and-scalability"></a><span data-ttu-id="535ea-188">需要高停机时间和可扩展性的应用程序</span><span class="sxs-lookup"><span data-stu-id="535ea-188">Applications requiring high uptime and scalability</span></span>

<span data-ttu-id="535ea-189">具有高高高高高高高扩展性和可扩展性要求的各个应用程序是使用微服务、容器和协调器的云原生体系结构的理想选择。</span><span class="sxs-lookup"><span data-stu-id="535ea-189">Individual applications that have high uptime and scalability requirements are ideal candidates for cloud-native architectures using microservices, containers, and orchestrators.</span></span> <span data-ttu-id="535ea-190">这些应用程序可以使用版本化环境在容器中开发，可以在生产前进行广泛测试，并且可以以零停机时间部署到生产中。</span><span class="sxs-lookup"><span data-stu-id="535ea-190">These applications can be developed in containers using versioned environments, can be extensively tested before going to production, and can be deployed to production with zero downtime.</span></span> <span data-ttu-id="535ea-191">使用 Kubernetes 群集可确保此类应用还可以按需扩展，并从节点故障中自动恢复。</span><span class="sxs-lookup"><span data-stu-id="535ea-191">The use of Kubernetes clusters ensures such apps can also scale on demand and recover automatically from node failures.</span></span>

### <a name="large-numbers-of-applications"></a><span data-ttu-id="535ea-192">大量应用</span><span class="sxs-lookup"><span data-stu-id="535ea-192">Large numbers of applications</span></span>

<span data-ttu-id="535ea-193">部署并随后必须维护大量应用程序的组织受益于容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="535ea-193">Organizations that deploy and must subsequently maintain large numbers of applications benefit from containers and orchestrators.</span></span> <span data-ttu-id="535ea-194">设置容器化环境和 Kubernetes 群集的前期工作主要是固定成本。</span><span class="sxs-lookup"><span data-stu-id="535ea-194">The up front effort of setting up containerized environments and Kubernetes clusters is primarily a fixed cost.</span></span> <span data-ttu-id="535ea-195">部署、维护和更新单个应用程序的成本随必须维护的应用程序数量而异。</span><span class="sxs-lookup"><span data-stu-id="535ea-195">Deploying, maintaining, and updating individual applications has a cost that varies with the number of applications that must be maintained.</span></span> <span data-ttu-id="535ea-196">除了数量相当少的应用程序之外，手动维护自定义应用程序的复杂性超过了使用容器和协调器实现解决方案的成本。</span><span class="sxs-lookup"><span data-stu-id="535ea-196">Beyond a certain fairly small number of applications, the complexity of maintaining custom applications manually exceeds the cost of implementing a solution using containers and orchestrators.</span></span>

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a><span data-ttu-id="535ea-197">何时应避免使用容器和协调器？</span><span class="sxs-lookup"><span data-stu-id="535ea-197">When should you avoid using containers and orchestrators?</span></span>

<span data-ttu-id="535ea-198">如果您不愿意或无法按照十二因子应用原则构建应用程序，则最好避免容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="535ea-198">If you're unwilling or unable to build your application following Twelve-Factor App principles, you'll probably be better off avoiding containers and orchestrators.</span></span> <span data-ttu-id="535ea-199">在这些情况下，最好使用基于 VM 的托管平台，或者可能采用一些混合系统，您可以在其中将某些功能引入单独的容器甚至无服务器功能。</span><span class="sxs-lookup"><span data-stu-id="535ea-199">In these cases, it may be best to move forward with a VM-based hosting platform, or possibly some hybrid system in which you can spin off certain pieces of functionality into separate containers or even serverless functions.</span></span>

## <a name="development-resources"></a><span data-ttu-id="535ea-200">开发资源</span><span class="sxs-lookup"><span data-stu-id="535ea-200">Development resources</span></span>

<span data-ttu-id="535ea-201">本节显示一个开发资源的简短列表，这些资源可帮助您开始为下一个应用程序使用容器和协调器。</span><span class="sxs-lookup"><span data-stu-id="535ea-201">This section shows a short list of development resources that may help you get started using containers and orchestrators for your next application.</span></span> <span data-ttu-id="535ea-202">如果您正在寻找有关如何设计云原生微服务体系结构应用的指导，请阅读本书的配套书[.NET 微服务：容器化 .NET 应用程序的体系结构](https://aka.ms/microservicesebook)。</span><span class="sxs-lookup"><span data-stu-id="535ea-202">If you're looking for guidance on how to design your cloud-native microservices architecture app, read this book's companion, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).</span></span>

### <a name="local-kubernetes-development"></a><span data-ttu-id="535ea-203">当地库伯内斯开发</span><span class="sxs-lookup"><span data-stu-id="535ea-203">Local Kubernetes Development</span></span>

<span data-ttu-id="535ea-204">Kubernetes 部署在生产环境中提供了巨大的价值，但您也可以在本地运行它们。</span><span class="sxs-lookup"><span data-stu-id="535ea-204">Kubernetes deployments provide great value in production environments, but you can also run them locally.</span></span> <span data-ttu-id="535ea-205">尽管大部分时间都能够独立处理单个应用或微服务是件好事，但有时能够像部署到生产时一样在本地运行整个系统是件好事。</span><span class="sxs-lookup"><span data-stu-id="535ea-205">Although much of the time it's good to be able to work on individual apps or microservices independently, sometimes it's good to be able to run the whole system locally just as it will run when deployed to production.</span></span> <span data-ttu-id="535ea-206">有几种方法可以实现此目的，其中两种方法是 Minikube 和 Docker 桌面。</span><span class="sxs-lookup"><span data-stu-id="535ea-206">There are several ways to achieve this, two of which are Minikube and Docker Desktop.</span></span> <span data-ttu-id="535ea-207">Visual Studio 还为 Docker 开发提供工具。</span><span class="sxs-lookup"><span data-stu-id="535ea-207">Visual Studio also provides tooling for Docker development.</span></span>

### <a name="minikube"></a><span data-ttu-id="535ea-208">Minikube</span><span class="sxs-lookup"><span data-stu-id="535ea-208">Minikube</span></span>

<span data-ttu-id="535ea-209">什么是米尼库贝？</span><span class="sxs-lookup"><span data-stu-id="535ea-209">What is Minikube?</span></span> <span data-ttu-id="535ea-210">Minikube 项目说："Minikube 在 macOS、Linux 和 Windows 上实现了本地 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="535ea-210">The Minikube project says "Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows."</span></span> <span data-ttu-id="535ea-211">其主要目标是"成为本地Kubernetes应用程序开发的最佳工具，并支持所有适合的Kubernetes功能。</span><span class="sxs-lookup"><span data-stu-id="535ea-211">Its primary goals are "to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit."</span></span> <span data-ttu-id="535ea-212">安装 Minikube 与 Docker 是分开的，但 Minikube 支持与 Docker 桌面支持不同的虚拟机管理程序。</span><span class="sxs-lookup"><span data-stu-id="535ea-212">Installing Minikube is separate from Docker, but Minikube supports different hypervisors than Docker Desktop supports.</span></span> <span data-ttu-id="535ea-213">Minikube 目前支持以下库伯奈斯功能：</span><span class="sxs-lookup"><span data-stu-id="535ea-213">The following Kubernetes features are currently supported by Minikube:</span></span>

- <span data-ttu-id="535ea-214">DNS</span><span class="sxs-lookup"><span data-stu-id="535ea-214">DNS</span></span>
- <span data-ttu-id="535ea-215">节点端口</span><span class="sxs-lookup"><span data-stu-id="535ea-215">NodePorts</span></span>
- <span data-ttu-id="535ea-216">配置映射和机密</span><span class="sxs-lookup"><span data-stu-id="535ea-216">ConfigMaps and secrets</span></span>
- <span data-ttu-id="535ea-217">仪表板</span><span class="sxs-lookup"><span data-stu-id="535ea-217">Dashboards</span></span>
- <span data-ttu-id="535ea-218">容器运行时：码头、rkt、CRI-O 和容器</span><span class="sxs-lookup"><span data-stu-id="535ea-218">Container runtimes: Docker, rkt, CRI-O, and containerd</span></span>
- <span data-ttu-id="535ea-219">启用容器网络接口 （CNI）</span><span class="sxs-lookup"><span data-stu-id="535ea-219">Enabling Container Network Interface (CNI)</span></span>
- <span data-ttu-id="535ea-220">流入量</span><span class="sxs-lookup"><span data-stu-id="535ea-220">Ingress</span></span>

<span data-ttu-id="535ea-221">安装 Minikube 后，可以通过运行`minikube start`命令快速开始使用它，该命令下载映像并启动本地 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="535ea-221">After installing Minikube, you can quickly start using it by running the `minikube start` command, which downloads an image and start the local Kubernetes cluster.</span></span> <span data-ttu-id="535ea-222">群集启动后，您将使用标准的 Kubernetes`kubectl`命令与其交互。</span><span class="sxs-lookup"><span data-stu-id="535ea-222">Once the cluster is started, you interact with it using the standard Kubernetes `kubectl` commands.</span></span>

### <a name="docker-desktop"></a><span data-ttu-id="535ea-223">Docker Desktop</span><span class="sxs-lookup"><span data-stu-id="535ea-223">Docker Desktop</span></span>

<span data-ttu-id="535ea-224">您还可以直接从 Windows 上的 Docker 桌面使用 Kubernetes。</span><span class="sxs-lookup"><span data-stu-id="535ea-224">You can also work with Kubernetes directly from Docker Desktop on Windows.</span></span> <span data-ttu-id="535ea-225">如果您使用的是 Windows 容器，这是您唯一的选择，也是非 Windows 容器的绝佳选择。</span><span class="sxs-lookup"><span data-stu-id="535ea-225">This is your only option if you're using Windows Containers, and is a great choice for non-Windows containers as well.</span></span> <span data-ttu-id="535ea-226">标准 Docker 桌面配置应用用于配置从 Docker 桌面运行的库伯内特。</span><span class="sxs-lookup"><span data-stu-id="535ea-226">The standard Docker Desktop configuration app is used to configure Kubernetes running from Docker Desktop.</span></span>

![在 Docker 桌面中配置库伯内斯](./media/docker-desktop-kubernetes.png)

<span data-ttu-id="535ea-228">**图3-4**。</span><span class="sxs-lookup"><span data-stu-id="535ea-228">**Figure 3-4**.</span></span> <span data-ttu-id="535ea-229">在 Docker 桌面中配置库伯内斯。</span><span class="sxs-lookup"><span data-stu-id="535ea-229">Configuring Kubernetes in Docker Desktop.</span></span>

<span data-ttu-id="535ea-230">Docker 桌面已经是本地配置和运行容器化应用的最常见工具。</span><span class="sxs-lookup"><span data-stu-id="535ea-230">Docker Desktop is already the most popular tool for configuring and running containerized apps locally.</span></span> <span data-ttu-id="535ea-231">使用 Docker Desktop 时，可以针对要部署到生产的完全相同的 Docker 容器映像集在本地进行开发。</span><span class="sxs-lookup"><span data-stu-id="535ea-231">When you work with Docker Desktop, you can develop locally against the exact same set of Docker container images that you'll deploy to production.</span></span> <span data-ttu-id="535ea-232">Docker 桌面旨在"在本地构建、测试和发货"容器化应用。</span><span class="sxs-lookup"><span data-stu-id="535ea-232">Docker Desktop is designed to "build, test, and ship" containerized apps locally.</span></span> <span data-ttu-id="535ea-233">将映像发送到映像注册表（如 Azure 容器注册表或 Docker Hub）后，Azure Kubernetes 服务 （AKS） 等服务将管理生产中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="535ea-233">Once the images have been shipped to an image registry like Azure Container Registry or Docker Hub, then services like Azure Kubernetes Service (AKS) manage the application in production.</span></span>

### <a name="visual-studio-docker-tooling"></a><span data-ttu-id="535ea-234">视觉工作室码头工具</span><span class="sxs-lookup"><span data-stu-id="535ea-234">Visual Studio Docker Tooling</span></span>

<span data-ttu-id="535ea-235">Visual Studio 支持 Web 应用程序的 Docker 开发。</span><span class="sxs-lookup"><span data-stu-id="535ea-235">Visual Studio supports Docker development for web applications.</span></span> <span data-ttu-id="535ea-236">创建新的ASP.NET核心应用程序时，您可以选择使用 Docker 支持来配置该应用程序，作为项目创建过程的一部分，如图 3-5 所示。</span><span class="sxs-lookup"><span data-stu-id="535ea-236">When you create a new ASP.NET Core application, you're given the option to configure it with Docker support as part of the project creation process, as shown in Figure 3-5.</span></span>

![可视化工作室启用 Docker 支持](./media/visual-studio-enable-docker-support.png)

<span data-ttu-id="535ea-238">**图3-5**。</span><span class="sxs-lookup"><span data-stu-id="535ea-238">**Figure 3-5**.</span></span> <span data-ttu-id="535ea-239">可视化工作室启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="535ea-239">Visual Studio Enable Docker Support</span></span>

<span data-ttu-id="535ea-240">选择此选项后，将使用 root 中的 项目`Dockerfile`创建项目，可用于在 Docker 容器中生成和托管应用。</span><span class="sxs-lookup"><span data-stu-id="535ea-240">When this option is selected, the project is created with a `Dockerfile` in its root, which can be used to build and host the app in a Docker container.</span></span> <span data-ttu-id="535ea-241">如图 3-6 所示有一个示例 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="535ea-241">An example Dockerfile is shown in Figure 3-6.</span></span>

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

<span data-ttu-id="535ea-242">**图3-6**.</span><span class="sxs-lookup"><span data-stu-id="535ea-242">**Figure 3-6**.</span></span> <span data-ttu-id="535ea-243">可视化工作室生成的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="535ea-243">Visual Studio generated Dockerfile</span></span>

<span data-ttu-id="535ea-244">应用运行时的默认行为也配置为使用 Docker。</span><span class="sxs-lookup"><span data-stu-id="535ea-244">The default behavior when the app runs is configured to use Docker as well.</span></span> <span data-ttu-id="535ea-245">图 3-7 显示了添加了 Docker 支持后创建的新ASP.NET核心项目中可用的不同运行选项。</span><span class="sxs-lookup"><span data-stu-id="535ea-245">Figure 3-7 shows the different run options available from a new ASP.NET Core project created with Docker support added.</span></span>

![可视化工作室 Docker 运行选项](./media/visual-studio-docker-run-options.png)

<span data-ttu-id="535ea-247">**图3-7**。</span><span class="sxs-lookup"><span data-stu-id="535ea-247">**Figure 3-7**.</span></span> <span data-ttu-id="535ea-248">可视化工作室 Docker 运行选项</span><span class="sxs-lookup"><span data-stu-id="535ea-248">Visual Studio Docker Run Options</span></span>

<span data-ttu-id="535ea-249">除了本地开发之外[，Azure 开发人员空间](https://docs.microsoft.com/azure/dev-spaces/)还为多个开发人员提供了一种在 Azure 中处理其自己的 Kubernets 配置的便捷方法。</span><span class="sxs-lookup"><span data-stu-id="535ea-249">In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way for multiple developers to work with their own Kubernetes configurations within Azure.</span></span> <span data-ttu-id="535ea-250">如图 3-7 所示，您还可以在 Azure 开发空间中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="535ea-250">As you can see in Figure 3-7, you can also run the application in Azure Dev Spaces.</span></span>

<span data-ttu-id="535ea-251">如果在创建 ASP.NET 酷应用程序时未将 Docker 支持添加到该应用程序，则始终可以在以后添加它。</span><span class="sxs-lookup"><span data-stu-id="535ea-251">If you don't add Docker support to your ASP.NET Core application when you create it, you can always add it later.</span></span> <span data-ttu-id="535ea-252">在可视化工作室解决方案资源管理器中，右键单击项目并选择 **"添加** > **Docker 支持**"，如图 3-8 所示。</span><span class="sxs-lookup"><span data-stu-id="535ea-252">From the Visual Studio Solution Explorer, right click on the project and select **Add** > **Docker Support**, as shown in Figure 3-8.</span></span>

![可视化工作室添加 Docker 支持](./media/visual-studio-add-docker-support.png)

<span data-ttu-id="535ea-254">**图3-8**。</span><span class="sxs-lookup"><span data-stu-id="535ea-254">**Figure 3-8**.</span></span> <span data-ttu-id="535ea-255">可视化工作室添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="535ea-255">Visual Studio Add Docker Support</span></span>

<span data-ttu-id="535ea-256">除了 Docker 支持之外，您还可以添加容器业务流程支持，如图 3-8 所示。</span><span class="sxs-lookup"><span data-stu-id="535ea-256">In addition to Docker support, you can also add Container Orchestration Support, also shown in Figure 3-8.</span></span> <span data-ttu-id="535ea-257">默认情况下，协调器使用库伯奈斯和赫尔姆。</span><span class="sxs-lookup"><span data-stu-id="535ea-257">By default, the orchestrator uses Kubernetes and Helm.</span></span> <span data-ttu-id="535ea-258">选择协调器后，将`azds.yaml`文件添加到项目根，并添加一个`charts`文件夹，其中包含用于配置应用程序并将应用程序部署到 Kubernetes 的 Helm 图表。</span><span class="sxs-lookup"><span data-stu-id="535ea-258">Once you've chosen the orchestrator, a `azds.yaml` file is added to the project root and a `charts` folder is added containing the Helm charts used to configure and deploy the application to Kubernetes.</span></span> <span data-ttu-id="535ea-259">图 3-9 显示了新项目中生成的文件。</span><span class="sxs-lookup"><span data-stu-id="535ea-259">Figure 3-9 shows the resulting files in a new project.</span></span>

![可视化工作室添加协调器支持](./media/visual-studio-add-orchestrator-support.png)

<span data-ttu-id="535ea-261">**图3-9**.</span><span class="sxs-lookup"><span data-stu-id="535ea-261">**Figure 3-9**.</span></span> <span data-ttu-id="535ea-262">可视化工作室添加协调器支持</span><span class="sxs-lookup"><span data-stu-id="535ea-262">Visual Studio Add Orchestrator Support</span></span>

## <a name="references"></a><span data-ttu-id="535ea-263">参考</span><span class="sxs-lookup"><span data-stu-id="535ea-263">References</span></span>

- [<span data-ttu-id="535ea-264">什么是 Kubernetes？</span><span class="sxs-lookup"><span data-stu-id="535ea-264">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="535ea-265">安装库伯内斯与米尼库贝</span><span class="sxs-lookup"><span data-stu-id="535ea-265">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="535ea-266">迷你库贝 vs Docker 桌面</span><span class="sxs-lookup"><span data-stu-id="535ea-266">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="535ea-267">Visual Studio Tools for Docker</span><span class="sxs-lookup"><span data-stu-id="535ea-267">Visual Studio Tools for Docker</span></span>](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
><span data-ttu-id="535ea-268">[上一页](scale-applications.md)
>[下一页](leverage-serverless-functions.md)</span><span class="sxs-lookup"><span data-stu-id="535ea-268">[Previous](scale-applications.md)
[Next](leverage-serverless-functions.md)</span></span>
