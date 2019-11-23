---
title: 服务网格-适用于 WCF 开发人员的 gRPC
description: 使用服务网格将请求路由并平衡到 Kubernetes 群集中的 gRPC 服务。
ms.date: 09/02/2019
ms.openlocfilehash: d20275082973f30bddbb342da90454401d4f019b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966972"
---
# <a name="service-meshes"></a>服务网格

服务网格是一种基础结构组件，控制网络中的路由服务请求。 服务网格可以处理 Kubernetes 群集中的各种网络级别问题，其中包括：

- 服务发现
- 负载均衡
- 容错
- 加密
- 监视

Kubernetes 服务网格通过向网格中包含的每个 pod 添加一个名为*挎斗 proxy*的额外容器来工作。 代理接管了所有入站和出站网络请求的处理，使网络的配置和管理与应用程序容器保持分离，在许多情况下，无需对应用程序代码进行任何更改。

获取[上一章节的示例](kubernetes.md#testing-the-application)，其中，来自 web 应用程序的 gRPC 请求全部路由到 gRPC 服务的单个实例。 出现这种情况的原因是，服务的主机名解析为 IP 地址，并且该 IP 地址缓存在 `HttpClientHandler` 实例的生存期内。 可以通过手动处理 DNS 查找或创建多个客户端来解决这种情况，但这会大大提高应用程序代码的复杂程度，而无需添加任何业务或客户价值。

使用服务网格，来自应用程序容器的请求将发送到挎斗代理，该代理可以在其他服务的所有实例中智能地分发这些请求。 网格还可以：

- 无缝响应服务的单个实例故障。
- 处理失败调用或超时的重试语义
- 将失败的请求重新路由到备用实例，而不会返回到客户端应用程序。

以下屏幕截图显示了使用 Linkerd 服务网格运行的 StockWeb 应用程序，不会更改应用程序代码，甚至使用的 Docker 映像。 所需的唯一更改是将批注添加到 `stockdata` 和 `stockweb` 服务的 YAML 文件中的部署。

![StockWeb Service 网格](media/service-mesh/stockweb-servicemesh-screenshot.png)

尽管从应用程序代码中的单个 `HttpClient` 实例开始，但从服务器列中可以看到，来自 StockWeb 应用程序的请求已路由到 StockData 服务的两个副本。 事实上，如果你查看代码，你会看到，StockData 服务的所有100请求同时使用同一个 `HttpClient` 实例进行，但对于服务网格，这些请求将在多个服务实例可用的情况下进行平衡。

服务网格仅适用于群集中的流量。 对于外部客户端，请参阅[下一章 "负载均衡](load-balancing.md)"。

## <a name="service-mesh-options"></a>服务网格选项

目前有三种常规用途的服务网格实现可用于 Kubernetes： Istio、Linkerd 和 Consul Connect。 所有三个都提供请求路由/代理、通信加密、复原、主机到主机身份验证和流量控制。

选择服务网格取决于多个因素：

- 组织对成本、符合性、付费支持计划等的特定要求。
- 群集的性质、其大小、部署的服务数量和群集网络中的流量。
- 轻松部署和管理网格，并将其用于服务。

每个服务网格的详细信息可从各自的网站获得。

- [**Istio** -istio.io](https://istio.io)
- [**Linkerd** -linkerd.io](https://linkerd.io)
- [**Consul** -consul.io/mesh.html](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a>示例：将 Linkerd 添加到部署

在此示例中，你将了解如何将 Linkerd service 网格与[上一节](kubernetes.md)中的*StockKube*应用程序一起使用。
若要执行此示例，需要[安装 LINKERD CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli)。 Windows 二进制文件可以从 GitHub 版本部分下载;请确保使用最新的**稳定**版本，而不是边缘版本之一。

安装 Linkerd CLI 后，按照 Linkerd 网站上的 [*入门*说明操作，在 Kubernetes 群集上安装 Linkerd 组件。 说明是直接的，安装只需几分钟即可完成本地 Kubernetes 实例。

### <a name="add-linkerd-to-kubernetes-deployments"></a>将 Linkerd 添加到 Kubernetes 部署

Linkerd CLI 提供 `inject` 命令，将必需的节和属性添加到 Kubernetes 文件。 您可以运行该命令并将输出写入到新文件中。

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

您可以检查新文件，以查看所做的更改。 对于部署对象，添加了元数据批注，告诉 Linkerd 在创建时将挎斗代理容器注入到 Pod。

还可以通过管道将 `linkerd inject` 命令的输出传递给直接 `kubectl`。 以下命令将在 PowerShell 或任何 Linux shell 中运行。

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a>在 Linkerd 仪表板中检查服务

使用 `linkerd` CLI 启动 Linkerd 仪表板。

```console
linkerd dashboard
```

该仪表板提供有关连接到网格的所有服务的详细信息。

![显示 StockKube 应用程序的 Linkerd 仪表板](media/service-mesh/linkerd-screenshot.png)

如果你按以下示例所示增加 StockData gRPC 服务的副本数，并在浏览器中刷新 StockWeb 页，则你应该会在 "服务器" 列中看到 Id 的混合，这表明请求由所有可用实例提供.

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
>[上一页](kubernetes.md)
>[下一页](load-balancing.md)
