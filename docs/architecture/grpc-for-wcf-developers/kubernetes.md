---
title: Kubernetes-WCF 开发人员 gRPC
description: 在 Kubernetes 群集中运行 ASP.NET Core gRPC 服务。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 819c761a7a55485612b7fb0c8b392971751d8724
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841575"
---
# <a name="kubernetes"></a><span data-ttu-id="f28a8-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f28a8-103">Kubernetes</span></span>

<span data-ttu-id="f28a8-104">尽管可以在 Docker 主机上手动运行容器，但对于可靠的生产系统，最好使用容器业务流程引擎来管理群集中多个服务器上运行的多个实例。</span><span class="sxs-lookup"><span data-stu-id="f28a8-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's preferable to use a Container Orchestration Engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="f28a8-105">提供各种容器业务流程引擎，包括 Kubernetes、Docker Swarm 和 Apache Mesos。</span><span class="sxs-lookup"><span data-stu-id="f28a8-105">There are various Container Orchestration Engines available, including Kubernetes, Docker Swarm and Apache Mesos.</span></span> <span data-ttu-id="f28a8-106">但在这些引擎中，Kubernetes 的使用幅度远远超出最大，因此，本章将重点介绍这一点。</span><span class="sxs-lookup"><span data-stu-id="f28a8-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="f28a8-107">Kubernetes 包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="f28a8-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="f28a8-108">**计划**在群集内的多个节点上运行容器，确保可用资源的平衡使用，在存在中断的情况下使容器保持运行，并处理对新版本的映像或新配置的滚动更新。</span><span class="sxs-lookup"><span data-stu-id="f28a8-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="f28a8-109">**运行状况检查**监视容器，以确保继续服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="f28a8-110">**DNS & 服务发现**处理群集中服务之间的路由。</span><span class="sxs-lookup"><span data-stu-id="f28a8-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="f28a8-111">**入口**公开选定的服务，通常在这些服务的实例之间提供负载平衡。</span><span class="sxs-lookup"><span data-stu-id="f28a8-111">**Ingress** exposes selected services externally, and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="f28a8-112">**资源管理**将存储等外部资源附加到容器。</span><span class="sxs-lookup"><span data-stu-id="f28a8-112">**Resource management** attaches external resources such as storage to containers.</span></span>

<span data-ttu-id="f28a8-113">本章详细介绍如何将 ASP.NET Core gRPC 服务和使用该服务的网站部署到 Kubernetes 群集中。</span><span class="sxs-lookup"><span data-stu-id="f28a8-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="f28a8-114">使用的示例应用程序可从 GitHub 上的[dotnet/grpc-for wcf-开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)存储库中获取。</span><span class="sxs-lookup"><span data-stu-id="f28a8-114">The sample application used is available from on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub,</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="f28a8-115">Kubernetes 术语</span><span class="sxs-lookup"><span data-stu-id="f28a8-115">Kubernetes terminology</span></span>

<span data-ttu-id="f28a8-116">Kubernetes 使用*所需状态配置*：使用 API 来描述对象 *（如 pod、* *部署*和*服务*），并*控制平面*负责在*群集*中的所有*节点*之间实现所需状态。</span><span class="sxs-lookup"><span data-stu-id="f28a8-116">Kubernetes uses *desired state configuration*: the API is used to describe objects such as *Pods*, *Deployments* and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="f28a8-117">Kubernetes 群集具有运行*KUBERNETES API*的*主*节点，可以通过编程方式或使用 `kubectl` 命令行工具进行通信。</span><span class="sxs-lookup"><span data-stu-id="f28a8-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which can be communicated with programmatically or using the `kubectl` command-line tool.</span></span> <span data-ttu-id="f28a8-118">`kubectl` 可以使用命令行参数来创建和管理对象，但最适合包含 Kubernetes 对象的声明数据的 YAML 文件。</span><span class="sxs-lookup"><span data-stu-id="f28a8-118">`kubectl` can create and manage objects using command-line arguments, but works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="f28a8-119">Kubernetes YAML 文件</span><span class="sxs-lookup"><span data-stu-id="f28a8-119">Kubernetes YAML files</span></span>

<span data-ttu-id="f28a8-120">每个 Kubernetes YAML 文件将具有至少三个顶级属性。</span><span class="sxs-lookup"><span data-stu-id="f28a8-120">Every Kubernetes YAML file will have at least three top-level properties.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="f28a8-121">`apiVersion` 属性用于指定文件的目标版本（以及哪个 API）。</span><span class="sxs-lookup"><span data-stu-id="f28a8-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="f28a8-122">`kind` 属性指定 YAML 表示的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="f28a8-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="f28a8-123">`metadata` 属性包含对象属性，如 `name`、`namespace`或 `labels`。</span><span class="sxs-lookup"><span data-stu-id="f28a8-123">The `metadata` property contains object properties such as `name`, `namespace`, or `labels`.</span></span>

<span data-ttu-id="f28a8-124">大多数 Kubernetes YAML 文件还会有一个 `spec` 部分，描述创建对象所需的资源和配置。</span><span class="sxs-lookup"><span data-stu-id="f28a8-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="f28a8-125">pod</span><span class="sxs-lookup"><span data-stu-id="f28a8-125">Pods</span></span>

<span data-ttu-id="f28a8-126">Pod 是 Kubernetes 中的基本执行单位。</span><span class="sxs-lookup"><span data-stu-id="f28a8-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="f28a8-127">它们可以运行多个容器，但也可用于运行单个容器。</span><span class="sxs-lookup"><span data-stu-id="f28a8-127">They can run multiple containers, but are also used to run single containers.</span></span> <span data-ttu-id="f28a8-128">Pod 还包括容器所需的任何存储资源，以及网络 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f28a8-128">The pod also includes any storage resources required by the container(s), and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="f28a8-129">Services</span><span class="sxs-lookup"><span data-stu-id="f28a8-129">Services</span></span>

<span data-ttu-id="f28a8-130">服务是一种元对象，用于描述 pod （或 pod 集），并提供一种在群集内访问这些对象的方式，如使用群集 DNS 服务将服务名称映射到一组 pod IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f28a8-130">Services are meta-objects that describe pods (or sets of pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="f28a8-131">部署</span><span class="sxs-lookup"><span data-stu-id="f28a8-131">Deployments</span></span>

<span data-ttu-id="f28a8-132">部署是 pod 的*说明状态*对象。</span><span class="sxs-lookup"><span data-stu-id="f28a8-132">Deployments are the *described state* objects for Pods.</span></span> <span data-ttu-id="f28a8-133">如果手动创建 Pod，则当其终止时，不会重新启动。</span><span class="sxs-lookup"><span data-stu-id="f28a8-133">If you create a Pod manually, when it terminates it won't be restarted.</span></span> <span data-ttu-id="f28a8-134">部署用于告知群集哪些 pod 和这些 pod 的副本数在当前时间运行。</span><span class="sxs-lookup"><span data-stu-id="f28a8-134">Deployments are used to tell the cluster which pods, and how many replicas of those pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="f28a8-135">其他对象</span><span class="sxs-lookup"><span data-stu-id="f28a8-135">Other objects</span></span>

<span data-ttu-id="f28a8-136">箱、服务和部署只是三个最基本的对象类型。</span><span class="sxs-lookup"><span data-stu-id="f28a8-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="f28a8-137">Kubernetes 群集管理了许多其他类型的对象。</span><span class="sxs-lookup"><span data-stu-id="f28a8-137">There are dozens of other types of object that are managed by a Kubernetes cluster.</span></span> <span data-ttu-id="f28a8-138">有关详细信息，请参阅[Kubernetes 概念](https://kubernetes.io/docs/concepts/)文档。</span><span class="sxs-lookup"><span data-stu-id="f28a8-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="f28a8-139">命名空间</span><span class="sxs-lookup"><span data-stu-id="f28a8-139">Namespaces</span></span>

<span data-ttu-id="f28a8-140">Kubernetes 群集旨在扩展到数百或数千个节点，并运行相似数量的服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes, and run similar numbers of services.</span></span> <span data-ttu-id="f28a8-141">若要避免对象名称之间的冲突，请使用命名空间将对象组合成较大的应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="f28a8-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="f28a8-142">Kubernetes 自己的服务在 `default` 命名空间中运行。</span><span class="sxs-lookup"><span data-stu-id="f28a8-142">Kubernetes own services run in a `default` namespace.</span></span> <span data-ttu-id="f28a8-143">所有用户对象都应在其自己的命名空间中创建，以避免与群集中的默认对象或其他租户发生冲突。</span><span class="sxs-lookup"><span data-stu-id="f28a8-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="f28a8-144">Kubernetes 入门</span><span class="sxs-lookup"><span data-stu-id="f28a8-144">Get started with Kubernetes</span></span>

<span data-ttu-id="f28a8-145">如果你运行的是适用于 Windows 或 macOS 的 Docker Desktop，则 Kubernetes 已可用。</span><span class="sxs-lookup"><span data-stu-id="f28a8-145">If you're running Docker Desktop for Windows or macOS, Kubernetes is already available.</span></span> <span data-ttu-id="f28a8-146">只需在 "设置" 窗口的 "Kubernetes" 部分中启用。</span><span class="sxs-lookup"><span data-stu-id="f28a8-146">Just enable it in the Kubernetes section of the Settings window.</span></span>

![在 Docker Desktop 中启用 Kubernetes](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="f28a8-148">若要在 Linux 中运行本地 Kubernetes 群集，请查看[minikube](https://github.com/kubernetes/minikube)或[MicroK8s](https://microk8s.io/) （如果 linux 分发支持[snap](https://snapcraft.io/)）。</span><span class="sxs-lookup"><span data-stu-id="f28a8-148">To run a local Kubernetes cluster in Linux, look at [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="f28a8-149">若要检查群集是否正在运行且可访问，请运行 `kubectl version` 命令。</span><span class="sxs-lookup"><span data-stu-id="f28a8-149">To check that your cluster is running and accessible, run the `kubectl version` command.</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="f28a8-150">在此示例中，`kubectl` CLI 和 Kubernetes 服务器都运行的是1.14.6 版本。</span><span class="sxs-lookup"><span data-stu-id="f28a8-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="f28a8-151">`kubectl` 的每个版本都应支持服务器的上一版本和下一版本，因此 `kubectl` 1.14 也应该与服务器版本1.13 和1.15 一起使用。</span><span class="sxs-lookup"><span data-stu-id="f28a8-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="f28a8-152">在 Kubernetes 上运行服务</span><span class="sxs-lookup"><span data-stu-id="f28a8-152">Run services on Kubernetes</span></span>

<span data-ttu-id="f28a8-153">该示例应用程序具有一个包含三个 YAML 文件的 `kube` 目录。</span><span class="sxs-lookup"><span data-stu-id="f28a8-153">The sample application has a `kube` directory containing three YAML files.</span></span> <span data-ttu-id="f28a8-154">`namespace.yml` 文件声明自定义命名空间，`stocks`。</span><span class="sxs-lookup"><span data-stu-id="f28a8-154">The `namespace.yml` file declares a custom namespace, `stocks`.</span></span> <span data-ttu-id="f28a8-155">`stockdata.yml` 文件声明 gRPC 应用程序的部署和服务，`stockweb.yml` 文件声明使用 gRPC 服务的 ASP.NET Core 3.0 MVC web 应用程序的部署和服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="f28a8-156">若要在 `kubectl`中使用 `YAML` 文件，请使用 `apply -f` 命令。</span><span class="sxs-lookup"><span data-stu-id="f28a8-156">To use a `YAML` file with `kubectl`, use the `apply -f` command.</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="f28a8-157">`apply` 命令将检查 YAML 文件的有效性并显示从 API 接收到的任何错误，但不会等待，直到创建了文件中声明的所有对象，因为这样做可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="f28a8-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created as this can take some time.</span></span> <span data-ttu-id="f28a8-158">使用带有相关对象类型的 `kubectl get` 命令来检查群集中的对象创建。</span><span class="sxs-lookup"><span data-stu-id="f28a8-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="f28a8-159">命名空间声明</span><span class="sxs-lookup"><span data-stu-id="f28a8-159">The namespace declaration</span></span>

<span data-ttu-id="f28a8-160">命名空间声明非常简单，只需分配 `name`。</span><span class="sxs-lookup"><span data-stu-id="f28a8-160">Namespace declaration is simple and requires only assigning a `name`.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="f28a8-161">使用 `kubectl` 应用 `namespace.yml` 文件，并检查命名空间是否已成功创建。</span><span class="sxs-lookup"><span data-stu-id="f28a8-161">Use `kubectl` to apply the `namespace.yml` file and check the namespace is created successfully.</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="f28a8-162">StockData 应用程序</span><span class="sxs-lookup"><span data-stu-id="f28a8-162">The StockData application</span></span>

<span data-ttu-id="f28a8-163">`stockdata.yml` 文件声明了两个对象：一个部署和一个服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="f28a8-164">StockData 部署</span><span class="sxs-lookup"><span data-stu-id="f28a8-164">The StockData Deployment</span></span>

<span data-ttu-id="f28a8-165">部署部分提供部署本身的 `spec`，包括所需的副本数，以及部署要创建和管理的 Pod 对象的 `template`。</span><span class="sxs-lookup"><span data-stu-id="f28a8-165">The Deployment part provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="f28a8-166">请注意，部署对象按 `apiVersion`中指定的 `apps` API 进行管理，而不是通过主 Kubernetes API 进行管理。</span><span class="sxs-lookup"><span data-stu-id="f28a8-166">Note that Deployment objects are managed with the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 1
  template:
    metadata:
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

<span data-ttu-id="f28a8-167">`spec.selector` 属性用于匹配正在运行的 pod 到部署。</span><span class="sxs-lookup"><span data-stu-id="f28a8-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="f28a8-168">Pod 的 `metadata.labels` 属性必须与 `matchLabels` 属性匹配，否则 API 调用将失败。</span><span class="sxs-lookup"><span data-stu-id="f28a8-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="f28a8-169">`template.spec` 节声明要运行的容器。</span><span class="sxs-lookup"><span data-stu-id="f28a8-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="f28a8-170">使用本地 Kubernetes 群集（如 Docker Desktop 提供的群集）时，可以指定在本地生成的映像，只要它们具有版本标记即可。</span><span class="sxs-lookup"><span data-stu-id="f28a8-170">When working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f28a8-171">默认情况下，Kubernetes 将始终检查并尝试请求新映像。</span><span class="sxs-lookup"><span data-stu-id="f28a8-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="f28a8-172">如果在其任何已知存储库中都找不到该映像，则创建 Pod 会失败。</span><span class="sxs-lookup"><span data-stu-id="f28a8-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="f28a8-173">若要使用本地映像，请将 `imagePullPolicy` 设置为 `Never`。</span><span class="sxs-lookup"><span data-stu-id="f28a8-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="f28a8-174">`ports` 属性指定应在 Pod 上发布的容器端口。</span><span class="sxs-lookup"><span data-stu-id="f28a8-174">The `ports` property specifies which container ports should be published on the Pod.</span></span>  <span data-ttu-id="f28a8-175">`stockservice` 映像将在标准 HTTP 端口上运行服务，因此会发布端口80。</span><span class="sxs-lookup"><span data-stu-id="f28a8-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="f28a8-176">`resources` 部分将资源限制应用于在 pod 中运行的容器。</span><span class="sxs-lookup"><span data-stu-id="f28a8-176">The `resources` section applies resource limits to the container running within the pod.</span></span> <span data-ttu-id="f28a8-177">这是一种很好的做法，因为它会阻止单个 pod 消耗节点上的所有可用 CPU 或内存。</span><span class="sxs-lookup"><span data-stu-id="f28a8-177">This is good practice as it prevents an individual pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="f28a8-178">ASP.NET Core 3.0 经过优化和优化，可在资源受限的容器中运行，`dotnet/core/aspnet` Docker 映像将设置环境变量，以告知 `dotnet` 运行时它在容器中。</span><span class="sxs-lookup"><span data-stu-id="f28a8-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers, and the `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="f28a8-179">StockData 服务</span><span class="sxs-lookup"><span data-stu-id="f28a8-179">The StockData Service</span></span>

<span data-ttu-id="f28a8-180">YAML 文件的服务部分声明了向群集中的 pod 提供访问权限的服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-180">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="f28a8-181">服务规范使用 `selector` 属性来匹配正在运行的 `Pods`，在本例中，查找标签 `run: stockdata`为的 pod。</span><span class="sxs-lookup"><span data-stu-id="f28a8-181">The Service spec uses the `selector` property to match running `Pods`, in this case looking for Pods with a label `run: stockdata`.</span></span> <span data-ttu-id="f28a8-182">匹配的 pod 上指定的 `port` 由指定的服务发布。</span><span class="sxs-lookup"><span data-stu-id="f28a8-182">The specified `port` on matching Pods are published by the named service.</span></span> <span data-ttu-id="f28a8-183">`stocks` 命名空间中运行的其他盒可以使用 `http://stockdata` 作为地址访问此服务上的 HTTP。</span><span class="sxs-lookup"><span data-stu-id="f28a8-183">Other Pods running in the `stocks` namespace can access HTTP on this service using `http://stockdata` as the address.</span></span> <span data-ttu-id="f28a8-184">在其他命名空间中运行的 pod 可以使用 `http://stockdata.stocks` 主机名。</span><span class="sxs-lookup"><span data-stu-id="f28a8-184">Pods running in other namespaces can use the `http://stockdata.stocks` hostname.</span></span> <span data-ttu-id="f28a8-185">可以使用[网络策略](https://kubernetes.io/docs/concepts/services-networking/network-policies/)来控制跨命名空间服务访问。</span><span class="sxs-lookup"><span data-stu-id="f28a8-185">You can control cross-namespace service access using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="f28a8-186">部署 StockData 应用程序</span><span class="sxs-lookup"><span data-stu-id="f28a8-186">Deploy the StockData application</span></span>

<span data-ttu-id="f28a8-187">使用 `kubectl` 应用 `stockdata.yml` 文件，并检查是否已创建部署和服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-187">Use `kubectl` to apply the `stockdata.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="f28a8-188">StockWeb 应用程序</span><span class="sxs-lookup"><span data-stu-id="f28a8-188">The StockWeb application</span></span>

<span data-ttu-id="f28a8-189">`stockweb.yml` 文件声明 MVC 应用程序的部署和服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-189">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="f28a8-190">环境变量</span><span class="sxs-lookup"><span data-stu-id="f28a8-190">Environment variables</span></span>

<span data-ttu-id="f28a8-191">部署对象的 "`env`" 部分指定要在运行 `stockweb:1.0.0` 映像的容器中设置的环境变量。</span><span class="sxs-lookup"><span data-stu-id="f28a8-191">The `env` section of the Deployment object specifies environment variables to be set in the container running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="f28a8-192">由于 EnvironmentVariables 配置提供程序， **`StockData__Address`** 环境变量将映射到 `StockData:Address` 配置设置。</span><span class="sxs-lookup"><span data-stu-id="f28a8-192">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="f28a8-193">此设置在名称之间使用双下划线分隔部分。</span><span class="sxs-lookup"><span data-stu-id="f28a8-193">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="f28a8-194">该地址使用在同一 Kubernetes 命名空间中运行的 `stockdata` 服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="f28a8-194">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="f28a8-195">**`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** 环境变量设置一个 <xref:System.AppContext> 开关，该开关为 <xref:System.Net.Http.HttpClient>启用未加密的 HTTP/2 连接。</span><span class="sxs-lookup"><span data-stu-id="f28a8-195">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="f28a8-196">此环境变量等效于在代码中设置开关，如此处所示。</span><span class="sxs-lookup"><span data-stu-id="f28a8-196">This environment variable is the equivalent of setting the switch in code as shown here.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="f28a8-197">使用开关的环境变量意味着可以轻松地更改设置，具体取决于应用程序运行的上下文。</span><span class="sxs-lookup"><span data-stu-id="f28a8-197">Using an environment variable for the switch means the setting can easily be changed depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="f28a8-198">服务类型</span><span class="sxs-lookup"><span data-stu-id="f28a8-198">Service types</span></span>

<span data-ttu-id="f28a8-199">若要使 Web 应用程序能够从群集外部访问，请使用 `type: NodePort` 属性。</span><span class="sxs-lookup"><span data-stu-id="f28a8-199">To make the Web application accessible from outside the cluster, the `type: NodePort` property is used.</span></span> <span data-ttu-id="f28a8-200">此属性类型会导致 Kubernetes 将服务上的端口80发布到群集外部网络套接字上的任意端口。</span><span class="sxs-lookup"><span data-stu-id="f28a8-200">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="f28a8-201">可以使用 `kubectl get service` 命令找到分配的端口。</span><span class="sxs-lookup"><span data-stu-id="f28a8-201">The port assigned can be found using the `kubectl get service` command.</span></span>

<span data-ttu-id="f28a8-202">不能从群集外部访问 `stockdata` 服务，因此它使用默认类型，`ClusterIP`。</span><span class="sxs-lookup"><span data-stu-id="f28a8-202">The `stockdata` service shouldn't be accessible from outside the cluster, so it used the default type, `ClusterIP`.</span></span>

<span data-ttu-id="f28a8-203">生产系统最有可能使用集成的负载均衡器向外部使用者公开公共应用程序。</span><span class="sxs-lookup"><span data-stu-id="f28a8-203">Production systems will most likely use an integrated load-balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="f28a8-204">以这种方式公开的服务应使用 `LoadBalancer` 类型。</span><span class="sxs-lookup"><span data-stu-id="f28a8-204">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="f28a8-205">有关服务类型的详细信息，请参阅[Kubernetes 的发布服务](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types)文档。</span><span class="sxs-lookup"><span data-stu-id="f28a8-205">For more information on service types, see the [Kubernetes' Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="f28a8-206">部署 StockWeb 应用程序</span><span class="sxs-lookup"><span data-stu-id="f28a8-206">Deploy the StockWeb application</span></span>

<span data-ttu-id="f28a8-207">使用 `kubectl` 应用 `stockweb.yml` 文件，并检查是否已创建部署和服务。</span><span class="sxs-lookup"><span data-stu-id="f28a8-207">Use `kubectl` to apply the `stockweb.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="f28a8-208">`get service` 命令的输出显示 HTTP 端口已发布到外部网络上的端口 `32564`;对于 Docker Desktop，此为 localhost。</span><span class="sxs-lookup"><span data-stu-id="f28a8-208">The output from the `get service` command shows that the HTTP port has been published to port `32564` on the external network; for Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="f28a8-209">可以通过浏览到 `http://localhost:32564`来访问该应用程序。</span><span class="sxs-lookup"><span data-stu-id="f28a8-209">The application can be accessed by browsing to `http://localhost:32564`.</span></span>

### <a name="testing-the-application"></a><span data-ttu-id="f28a8-210">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="f28a8-210">Testing the application</span></span>

<span data-ttu-id="f28a8-211">StockWeb 应用程序显示从简单的请求-答复服务中检索到的 NASDAQ 股票列表。</span><span class="sxs-lookup"><span data-stu-id="f28a8-211">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="f28a8-212">出于演示目的，每行还显示返回它的服务实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f28a8-212">For demonstration purposes, each line also shows the unique ID of the service instance that returned it.</span></span>

![StockWeb 屏幕快照](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="f28a8-214">如果 `stockdata` 服务的副本数已增加，则可能希望**服务器**值从行更改为行，但事实上，始终从同一实例返回所有100记录。</span><span class="sxs-lookup"><span data-stu-id="f28a8-214">If the number of replicas of the `stockdata` service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="f28a8-215">如果每隔几秒刷新一次页面，则服务器 ID 保持不变。</span><span class="sxs-lookup"><span data-stu-id="f28a8-215">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="f28a8-216">为什么会发生这种情况？</span><span class="sxs-lookup"><span data-stu-id="f28a8-216">Why does this happen?</span></span> <span data-ttu-id="f28a8-217">此处提供两个因素。</span><span class="sxs-lookup"><span data-stu-id="f28a8-217">There are two factors at play here.</span></span>

<span data-ttu-id="f28a8-218">首先，Kubernetes 服务发现系统默认使用 "轮循机制" 负载均衡。</span><span class="sxs-lookup"><span data-stu-id="f28a8-218">First, the Kubernetes service discovery system uses "round-robin" load-balancing by default.</span></span> <span data-ttu-id="f28a8-219">第一次查询 DNS 服务器时，它将返回服务的第一个匹配的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f28a8-219">The first time the DNS server is queried, it will return the first matching IP address for the service.</span></span> <span data-ttu-id="f28a8-220">下一次是列表中的下一个 IP 地址，依此类推，直到结束，此时它会循环回开始。</span><span class="sxs-lookup"><span data-stu-id="f28a8-220">The next time, the next IP address in the list, and so on, until the end, at which point it loops back to the start.</span></span>

<span data-ttu-id="f28a8-221">其次，用于 StockWeb 应用程序的 gRPC 客户端的 `HttpClient` 由[ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)创建和管理，该客户端的单个实例用于每次调用页面。</span><span class="sxs-lookup"><span data-stu-id="f28a8-221">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="f28a8-222">客户端只进行一次 DNS 查找，因此所有请求都将路由到相同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f28a8-222">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="f28a8-223">此外，由于出于性能方面的原因缓存了 `HttpClientHandler`，因此快速连续的多个请求将*所有*使用相同的 IP 地址，直到缓存的 DNS 条目过期，或由于某种原因释放了处理程序实例。</span><span class="sxs-lookup"><span data-stu-id="f28a8-223">Furthermore, because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="f28a8-224">这意味着，默认情况下，对 gRPC 服务的请求不会在群集中该服务的所有实例间平衡。</span><span class="sxs-lookup"><span data-stu-id="f28a8-224">This means that by default requests to a gRPC service aren't balanced across all instances of that service in the cluster.</span></span> <span data-ttu-id="f28a8-225">不同的使用者将使用不同的实例，但这并不保证请求的良好分布和资源的平衡使用。</span><span class="sxs-lookup"><span data-stu-id="f28a8-225">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests and a balanced use of resources.</span></span>

<span data-ttu-id="f28a8-226">下一章[服务网格](service-mesh.md)将介绍如何解决此问题。</span><span class="sxs-lookup"><span data-stu-id="f28a8-226">The next chapter, [Service Meshes](service-mesh.md), will look at how to address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f28a8-227">[上一页](docker.md)
>[下一页](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="f28a8-227">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
