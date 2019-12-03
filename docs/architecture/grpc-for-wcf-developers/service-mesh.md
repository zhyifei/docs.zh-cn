---
title: 服务网格-适用于 WCF 开发人员的 gRPC
description: 使用服务网格将请求路由并平衡到 Kubernetes 群集中的 gRPC 服务。
ms.date: 09/02/2019
ms.openlocfilehash: cc4855b1ed27e29076e4f13f5c5d3dffa63a6554
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711278"
---
# <a name="service-meshes"></a><span data-ttu-id="ba73c-103">服务网格</span><span class="sxs-lookup"><span data-stu-id="ba73c-103">Service meshes</span></span>

<span data-ttu-id="ba73c-104">服务网格是一种基础结构组件，控制网络中的路由服务请求。</span><span class="sxs-lookup"><span data-stu-id="ba73c-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="ba73c-105">服务网格可以处理 Kubernetes 群集中的各种网络级别问题，其中包括：</span><span class="sxs-lookup"><span data-stu-id="ba73c-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="ba73c-106">服务发现</span><span class="sxs-lookup"><span data-stu-id="ba73c-106">Service discovery</span></span>
- <span data-ttu-id="ba73c-107">负载平衡</span><span class="sxs-lookup"><span data-stu-id="ba73c-107">Load balancing</span></span>
- <span data-ttu-id="ba73c-108">容错</span><span class="sxs-lookup"><span data-stu-id="ba73c-108">Fault tolerance</span></span>
- <span data-ttu-id="ba73c-109">加密</span><span class="sxs-lookup"><span data-stu-id="ba73c-109">Encryption</span></span>
- <span data-ttu-id="ba73c-110">监视</span><span class="sxs-lookup"><span data-stu-id="ba73c-110">Monitoring</span></span>

<span data-ttu-id="ba73c-111">Kubernetes 服务网格通过向网格中包含的每个 pod 添加一个名为*挎斗 proxy*的额外容器来工作。</span><span class="sxs-lookup"><span data-stu-id="ba73c-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="ba73c-112">代理接管了所有入站和出站网络请求的处理，使网络的配置和管理与应用程序容器保持分离，在许多情况下，无需对应用程序代码进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="ba73c-112">The proxy takes over handling all inbound and outbound network requests, allowing configuration and management of networking matters to be kept separate from the application containers and, in many cases, without requiring any changes to the application code.</span></span>

<span data-ttu-id="ba73c-113">获取[上一章节的示例](kubernetes.md#test-the-application)，其中，来自 web 应用程序的 gRPC 请求全部路由到 gRPC 服务的单个实例。</span><span class="sxs-lookup"><span data-stu-id="ba73c-113">Take the [previous chapter's example](kubernetes.md#test-the-application), where the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="ba73c-114">出现这种情况的原因是，服务的主机名解析为 IP 地址，并且该 IP 地址缓存在 `HttpClientHandler` 实例的生存期内。</span><span class="sxs-lookup"><span data-stu-id="ba73c-114">This happens because the service's hostname is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="ba73c-115">可以通过手动处理 DNS 查找或创建多个客户端来解决这种情况，但这会大大提高应用程序代码的复杂程度，而无需添加任何业务或客户价值。</span><span class="sxs-lookup"><span data-stu-id="ba73c-115">It might be possible to work around this by handling DNS lookups manually or creating multiple clients, but this would complicate the application code considerably without adding any business or customer value.</span></span>

<span data-ttu-id="ba73c-116">使用服务网格，来自应用程序容器的请求将发送到挎斗代理，该代理可以在其他服务的所有实例中智能地分发这些请求。</span><span class="sxs-lookup"><span data-stu-id="ba73c-116">Using a service mesh, the requests from the application container are sent to the sidecar proxy, which can distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="ba73c-117">网格还可以：</span><span class="sxs-lookup"><span data-stu-id="ba73c-117">The mesh can also:</span></span>

- <span data-ttu-id="ba73c-118">无缝响应服务的单个实例故障。</span><span class="sxs-lookup"><span data-stu-id="ba73c-118">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="ba73c-119">处理失败调用或超时的重试语义</span><span class="sxs-lookup"><span data-stu-id="ba73c-119">Handle retry semantics for failed calls or timeouts</span></span>
- <span data-ttu-id="ba73c-120">将失败的请求重新路由到备用实例，而不会返回到客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba73c-120">Reroute failed requests to an alternate instance without returning to the client application at all.</span></span>

<span data-ttu-id="ba73c-121">以下屏幕截图显示了使用 Linkerd 服务网格运行的 StockWeb 应用程序，不会更改应用程序代码，甚至使用的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="ba73c-121">The following screenshot shows the StockWeb application running with the Linkerd service mesh, with no changes to the application code, or even the Docker image being used.</span></span> <span data-ttu-id="ba73c-122">所需的唯一更改是将批注添加到 `stockdata` 和 `stockweb` 服务的 YAML 文件中的部署。</span><span class="sxs-lookup"><span data-stu-id="ba73c-122">The only change required was the addition of an annotation to the Deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![StockWeb Service 网格](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="ba73c-124">尽管从应用程序代码中的单个 `HttpClient` 实例开始，但从服务器列中可以看到，来自 StockWeb 应用程序的请求已路由到 StockData 服务的两个副本。</span><span class="sxs-lookup"><span data-stu-id="ba73c-124">You can see from the Server column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="ba73c-125">事实上，如果你查看代码，你会看到，StockData 服务的所有100请求同时使用同一个 `HttpClient` 实例进行，但对于服务网格，这些请求将在多个服务实例可用的情况下进行平衡。</span><span class="sxs-lookup"><span data-stu-id="ba73c-125">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously using the same `HttpClient` instance, yet with the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="ba73c-126">服务网格仅适用于群集中的流量。</span><span class="sxs-lookup"><span data-stu-id="ba73c-126">Service meshes only apply to traffic within a cluster.</span></span> <span data-ttu-id="ba73c-127">对于外部客户端，请参阅[下一章 "负载均衡](load-balancing.md)"。</span><span class="sxs-lookup"><span data-stu-id="ba73c-127">For external clients, see [the next chapter, Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="ba73c-128">服务网格选项</span><span class="sxs-lookup"><span data-stu-id="ba73c-128">Service mesh options</span></span>

<span data-ttu-id="ba73c-129">目前有三种常规用途的服务网格实现可用于 Kubernetes： Istio、Linkerd 和 Consul Connect。</span><span class="sxs-lookup"><span data-stu-id="ba73c-129">There are three general-purpose service mesh implementations currently available for use with Kubernetes: Istio, Linkerd, and Consul Connect.</span></span> <span data-ttu-id="ba73c-130">所有三个都提供请求路由/代理、通信加密、复原、主机到主机身份验证和流量控制。</span><span class="sxs-lookup"><span data-stu-id="ba73c-130">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="ba73c-131">选择服务网格取决于多个因素：</span><span class="sxs-lookup"><span data-stu-id="ba73c-131">Choosing a service mesh depends multiple factors:</span></span>

- <span data-ttu-id="ba73c-132">组织对成本、符合性、付费支持计划等的特定要求。</span><span class="sxs-lookup"><span data-stu-id="ba73c-132">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="ba73c-133">群集的性质、其大小、部署的服务数量和群集网络中的流量。</span><span class="sxs-lookup"><span data-stu-id="ba73c-133">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="ba73c-134">轻松部署和管理网格，并将其用于服务。</span><span class="sxs-lookup"><span data-stu-id="ba73c-134">Ease of deploying and managing the mesh and using it with services.</span></span>

<span data-ttu-id="ba73c-135">每个服务网格的详细信息可从各自的网站获得。</span><span class="sxs-lookup"><span data-stu-id="ba73c-135">More information on each service mesh is available from their respective websites.</span></span>

- [<span data-ttu-id="ba73c-136">**Istio** -istio.io</span><span class="sxs-lookup"><span data-stu-id="ba73c-136">**Istio** - istio.io</span></span>](https://istio.io)
- [<span data-ttu-id="ba73c-137">**Linkerd** -linkerd.io</span><span class="sxs-lookup"><span data-stu-id="ba73c-137">**Linkerd** - linkerd.io</span></span>](https://linkerd.io)
- [<span data-ttu-id="ba73c-138">**Consul** -consul.io/mesh.html</span><span class="sxs-lookup"><span data-stu-id="ba73c-138">**Consul** - consul.io/mesh.html</span></span>](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="ba73c-139">示例：将 Linkerd 添加到部署</span><span class="sxs-lookup"><span data-stu-id="ba73c-139">Example: add Linkerd to a deployment</span></span>

<span data-ttu-id="ba73c-140">在此示例中，你将了解如何将 Linkerd service 网格与[上一节](kubernetes.md)中的*StockKube*应用程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="ba73c-140">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="ba73c-141">若要执行此示例，需要[安装 LINKERD CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli)。</span><span class="sxs-lookup"><span data-stu-id="ba73c-141">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="ba73c-142">Windows 二进制文件可以从 GitHub 版本部分下载;请确保使用最新的**稳定**版本，而不是边缘版本之一。</span><span class="sxs-lookup"><span data-stu-id="ba73c-142">Windows binaries can be downloaded from the GitHub releases section; make sure to use the most recent **stable** release and not one of the edge releases.</span></span>

<span data-ttu-id="ba73c-143">安装 Linkerd CLI 后，按照 Linkerd 网站上的 [*入门*说明操作，在 Kubernetes 群集上安装 Linkerd 组件。</span><span class="sxs-lookup"><span data-stu-id="ba73c-143">With the Linkerd CLI installed, follow the [*Getting Started* instructions on the Linkerd web site] to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="ba73c-144">说明是直接的，安装只需几分钟即可完成本地 Kubernetes 实例。</span><span class="sxs-lookup"><span data-stu-id="ba73c-144">The instructions are straight-forward and installation should only take a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="ba73c-145">将 Linkerd 添加到 Kubernetes 部署</span><span class="sxs-lookup"><span data-stu-id="ba73c-145">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="ba73c-146">Linkerd CLI 提供 `inject` 命令，将必需的节和属性添加到 Kubernetes 文件。</span><span class="sxs-lookup"><span data-stu-id="ba73c-146">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="ba73c-147">您可以运行该命令并将输出写入到新文件中。</span><span class="sxs-lookup"><span data-stu-id="ba73c-147">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="ba73c-148">您可以检查新文件，以查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ba73c-148">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="ba73c-149">对于部署对象，添加了元数据批注，告诉 Linkerd 在创建时将挎斗代理容器注入到 Pod。</span><span class="sxs-lookup"><span data-stu-id="ba73c-149">For Deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the Pod when it's created.</span></span>

<span data-ttu-id="ba73c-150">还可以通过管道将 `linkerd inject` 命令的输出传递给直接 `kubectl`。</span><span class="sxs-lookup"><span data-stu-id="ba73c-150">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="ba73c-151">以下命令将在 PowerShell 或任何 Linux shell 中运行。</span><span class="sxs-lookup"><span data-stu-id="ba73c-151">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="ba73c-152">在 Linkerd 仪表板中检查服务</span><span class="sxs-lookup"><span data-stu-id="ba73c-152">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="ba73c-153">使用 `linkerd` CLI 启动 Linkerd 仪表板。</span><span class="sxs-lookup"><span data-stu-id="ba73c-153">Launch the Linkerd dashboard using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="ba73c-154">该仪表板提供有关连接到网格的所有服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ba73c-154">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![显示 StockKube 应用程序的 Linkerd 仪表板](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="ba73c-156">如果你按以下示例所示增加 StockData gRPC 服务的副本数，并在浏览器中刷新 StockWeb 页，则你应该会在 "服务器" 列中看到 Id 的混合，这表明请求由所有可用实例提供.</span><span class="sxs-lookup"><span data-stu-id="ba73c-156">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the Server column, indicating that requests are being served by all the available instances.</span></span>

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
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
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

>[!div class="step-by-step"]
><span data-ttu-id="ba73c-157">[上一页](kubernetes.md)
>[下一页](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="ba73c-157">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
