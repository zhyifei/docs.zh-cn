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
# <a name="kubernetes"></a>Kubernetes

尽管可以在 Docker 主机上手动运行容器，但对于可靠的生产系统，最好使用容器业务流程引擎来管理群集中多个服务器上运行的多个实例。 提供各种容器业务流程引擎，包括 Kubernetes、Docker Swarm 和 Apache Mesos。 但在这些引擎中，Kubernetes 的使用幅度远远超出最大，因此，本章将重点介绍这一点。

Kubernetes 包括以下功能：

- **计划**在群集内的多个节点上运行容器，确保可用资源的平衡使用，在存在中断的情况下使容器保持运行，并处理对新版本的映像或新配置的滚动更新。
- **运行状况检查**监视容器，以确保继续服务。
- **DNS & 服务发现**处理群集中服务之间的路由。
- **入口**公开选定的服务，通常在这些服务的实例之间提供负载平衡。
- **资源管理**将存储等外部资源附加到容器。

本章详细介绍如何将 ASP.NET Core gRPC 服务和使用该服务的网站部署到 Kubernetes 群集中。 使用的示例应用程序可从 GitHub 上的[dotnet/grpc-for wcf-开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)存储库中获取。

## <a name="kubernetes-terminology"></a>Kubernetes 术语

Kubernetes 使用*所需状态配置*：使用 API 来描述对象 *（如 pod、* *部署*和*服务*），并*控制平面*负责在*群集*中的所有*节点*之间实现所需状态。 Kubernetes 群集具有运行*KUBERNETES API*的*主*节点，可以通过编程方式或使用 `kubectl` 命令行工具进行通信。 `kubectl` 可以使用命令行参数来创建和管理对象，但最适合包含 Kubernetes 对象的声明数据的 YAML 文件。

### <a name="kubernetes-yaml-files"></a>Kubernetes YAML 文件

每个 Kubernetes YAML 文件将具有至少三个顶级属性。

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

`apiVersion` 属性用于指定文件的目标版本（以及哪个 API）。 `kind` 属性指定 YAML 表示的对象的类型。 `metadata` 属性包含对象属性，如 `name`、`namespace`或 `labels`。

大多数 Kubernetes YAML 文件还会有一个 `spec` 部分，描述创建对象所需的资源和配置。

### <a name="pods"></a>pod

Pod 是 Kubernetes 中的基本执行单位。 它们可以运行多个容器，但也可用于运行单个容器。 Pod 还包括容器所需的任何存储资源，以及网络 IP 地址。

### <a name="services"></a>Services

服务是一种元对象，用于描述 pod （或 pod 集），并提供一种在群集内访问这些对象的方式，如使用群集 DNS 服务将服务名称映射到一组 pod IP 地址。

### <a name="deployments"></a>部署

部署是 pod 的*说明状态*对象。 如果手动创建 Pod，则当其终止时，不会重新启动。 部署用于告知群集哪些 pod 和这些 pod 的副本数在当前时间运行。

### <a name="other-objects"></a>其他对象

箱、服务和部署只是三个最基本的对象类型。 Kubernetes 群集管理了许多其他类型的对象。 有关详细信息，请参阅[Kubernetes 概念](https://kubernetes.io/docs/concepts/)文档。

### <a name="namespaces"></a>命名空间

Kubernetes 群集旨在扩展到数百或数千个节点，并运行相似数量的服务。 若要避免对象名称之间的冲突，请使用命名空间将对象组合成较大的应用程序的一部分。 Kubernetes 自己的服务在 `default` 命名空间中运行。 所有用户对象都应在其自己的命名空间中创建，以避免与群集中的默认对象或其他租户发生冲突。

## <a name="get-started-with-kubernetes"></a>Kubernetes 入门

如果你运行的是适用于 Windows 或 macOS 的 Docker Desktop，则 Kubernetes 已可用。 只需在 "设置" 窗口的 "Kubernetes" 部分中启用。

![在 Docker Desktop 中启用 Kubernetes](media/kubernetes/enable-kubernetes-docker-desktop.png)

若要在 Linux 中运行本地 Kubernetes 群集，请查看[minikube](https://github.com/kubernetes/minikube)或[MicroK8s](https://microk8s.io/) （如果 linux 分发支持[snap](https://snapcraft.io/)）。

若要检查群集是否正在运行且可访问，请运行 `kubectl version` 命令。

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

在此示例中，`kubectl` CLI 和 Kubernetes 服务器都运行的是1.14.6 版本。 `kubectl` 的每个版本都应支持服务器的上一版本和下一版本，因此 `kubectl` 1.14 也应该与服务器版本1.13 和1.15 一起使用。

## <a name="run-services-on-kubernetes"></a>在 Kubernetes 上运行服务

该示例应用程序具有一个包含三个 YAML 文件的 `kube` 目录。 `namespace.yml` 文件声明自定义命名空间，`stocks`。 `stockdata.yml` 文件声明 gRPC 应用程序的部署和服务，`stockweb.yml` 文件声明使用 gRPC 服务的 ASP.NET Core 3.0 MVC web 应用程序的部署和服务。

若要在 `kubectl`中使用 `YAML` 文件，请使用 `apply -f` 命令。

```console
kubectl apply -f object.yml
```

`apply` 命令将检查 YAML 文件的有效性并显示从 API 接收到的任何错误，但不会等待，直到创建了文件中声明的所有对象，因为这样做可能需要一些时间。 使用带有相关对象类型的 `kubectl get` 命令来检查群集中的对象创建。

### <a name="the-namespace-declaration"></a>命名空间声明

命名空间声明非常简单，只需分配 `name`。

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

使用 `kubectl` 应用 `namespace.yml` 文件，并检查命名空间是否已成功创建。

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a>StockData 应用程序

`stockdata.yml` 文件声明了两个对象：一个部署和一个服务。

#### <a name="the-stockdata-deployment"></a>StockData 部署

部署部分提供部署本身的 `spec`，包括所需的副本数，以及部署要创建和管理的 Pod 对象的 `template`。 请注意，部署对象按 `apiVersion`中指定的 `apps` API 进行管理，而不是通过主 Kubernetes API 进行管理。

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

`spec.selector` 属性用于匹配正在运行的 pod 到部署。 Pod 的 `metadata.labels` 属性必须与 `matchLabels` 属性匹配，否则 API 调用将失败。

`template.spec` 节声明要运行的容器。 使用本地 Kubernetes 群集（如 Docker Desktop 提供的群集）时，可以指定在本地生成的映像，只要它们具有版本标记即可。

> [!IMPORTANT]
> 默认情况下，Kubernetes 将始终检查并尝试请求新映像。 如果在其任何已知存储库中都找不到该映像，则创建 Pod 会失败。 若要使用本地映像，请将 `imagePullPolicy` 设置为 `Never`。

`ports` 属性指定应在 Pod 上发布的容器端口。  `stockservice` 映像将在标准 HTTP 端口上运行服务，因此会发布端口80。

`resources` 部分将资源限制应用于在 pod 中运行的容器。 这是一种很好的做法，因为它会阻止单个 pod 消耗节点上的所有可用 CPU 或内存。

> [!NOTE]
> ASP.NET Core 3.0 经过优化和优化，可在资源受限的容器中运行，`dotnet/core/aspnet` Docker 映像将设置环境变量，以告知 `dotnet` 运行时它在容器中。

#### <a name="the-stockdata-service"></a>StockData 服务

YAML 文件的服务部分声明了向群集中的 pod 提供访问权限的服务。

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

服务规范使用 `selector` 属性来匹配正在运行的 `Pods`，在本例中，查找标签 `run: stockdata`为的 pod。 匹配的 pod 上指定的 `port` 由指定的服务发布。 `stocks` 命名空间中运行的其他盒可以使用 `http://stockdata` 作为地址访问此服务上的 HTTP。 在其他命名空间中运行的 pod 可以使用 `http://stockdata.stocks` 主机名。 可以使用[网络策略](https://kubernetes.io/docs/concepts/services-networking/network-policies/)来控制跨命名空间服务访问。

#### <a name="deploy-the-stockdata-application"></a>部署 StockData 应用程序

使用 `kubectl` 应用 `stockdata.yml` 文件，并检查是否已创建部署和服务。

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

### <a name="the-stockweb-application"></a>StockWeb 应用程序

`stockweb.yml` 文件声明 MVC 应用程序的部署和服务。

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

#### <a name="environment-variables"></a>环境变量

部署对象的 "`env`" 部分指定要在运行 `stockweb:1.0.0` 映像的容器中设置的环境变量。

由于 EnvironmentVariables 配置提供程序， **`StockData__Address`** 环境变量将映射到 `StockData:Address` 配置设置。 此设置在名称之间使用双下划线分隔部分。 该地址使用在同一 Kubernetes 命名空间中运行的 `stockdata` 服务的服务名称。

**`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** 环境变量设置一个 <xref:System.AppContext> 开关，该开关为 <xref:System.Net.Http.HttpClient>启用未加密的 HTTP/2 连接。 此环境变量等效于在代码中设置开关，如此处所示。

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

使用开关的环境变量意味着可以轻松地更改设置，具体取决于应用程序运行的上下文。

#### <a name="service-types"></a>服务类型

若要使 Web 应用程序能够从群集外部访问，请使用 `type: NodePort` 属性。 此属性类型会导致 Kubernetes 将服务上的端口80发布到群集外部网络套接字上的任意端口。 可以使用 `kubectl get service` 命令找到分配的端口。

不能从群集外部访问 `stockdata` 服务，因此它使用默认类型，`ClusterIP`。

生产系统最有可能使用集成的负载均衡器向外部使用者公开公共应用程序。 以这种方式公开的服务应使用 `LoadBalancer` 类型。

有关服务类型的详细信息，请参阅[Kubernetes 的发布服务](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types)文档。

#### <a name="deploy-the-stockweb-application"></a>部署 StockWeb 应用程序

使用 `kubectl` 应用 `stockweb.yml` 文件，并检查是否已创建部署和服务。

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

`get service` 命令的输出显示 HTTP 端口已发布到外部网络上的端口 `32564`;对于 Docker Desktop，此为 localhost。 可以通过浏览到 `http://localhost:32564`来访问该应用程序。

### <a name="testing-the-application"></a>测试应用程序

StockWeb 应用程序显示从简单的请求-答复服务中检索到的 NASDAQ 股票列表。 出于演示目的，每行还显示返回它的服务实例的唯一 ID。

![StockWeb 屏幕快照](media/kubernetes/stockweb-screenshot.png)

如果 `stockdata` 服务的副本数已增加，则可能希望**服务器**值从行更改为行，但事实上，始终从同一实例返回所有100记录。 如果每隔几秒刷新一次页面，则服务器 ID 保持不变。 为什么会发生这种情况？ 此处提供两个因素。

首先，Kubernetes 服务发现系统默认使用 "轮循机制" 负载均衡。 第一次查询 DNS 服务器时，它将返回服务的第一个匹配的 IP 地址。 下一次是列表中的下一个 IP 地址，依此类推，直到结束，此时它会循环回开始。

其次，用于 StockWeb 应用程序的 gRPC 客户端的 `HttpClient` 由[ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)创建和管理，该客户端的单个实例用于每次调用页面。 客户端只进行一次 DNS 查找，因此所有请求都将路由到相同的 IP 地址。 此外，由于出于性能方面的原因缓存了 `HttpClientHandler`，因此快速连续的多个请求将*所有*使用相同的 IP 地址，直到缓存的 DNS 条目过期，或由于某种原因释放了处理程序实例。

这意味着，默认情况下，对 gRPC 服务的请求不会在群集中该服务的所有实例间平衡。 不同的使用者将使用不同的实例，但这并不保证请求的良好分布和资源的平衡使用。

下一章[服务网格](service-mesh.md)将介绍如何解决此问题。

>[!div class="step-by-step"]
>[上一页](docker.md)
>[下一页](service-mesh.md)
