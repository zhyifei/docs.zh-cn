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
# <a name="leveraging-containers-and-orchestrators"></a>利用容器和协调器

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

容器和协调器旨在解决单一部署方法常见的问题。

## <a name="challenges-with-monolithic-deployments"></a>单一部署难题

传统上，大多数应用程序都部署为单个单元。 此类应用程序称为单体架构。 这种将应用程序作为单一单元进行部署的通用方法，即使它们由多个模块或程序集组成，也称为单片体系结构，如图3-1 所示。

![整体体系结构。](./media/monolithic-architecture.png)

**图 3-1**。 整体体系结构。

尽管它们具有简易性的优点，但单一体系结构面临着许多挑战：

### <a name="deployments"></a>部署

部署到单一应用程序通常需要重新启动整个应用程序，即使只替换一个小模块。 根据托管应用程序的计算机的数目，这可能会导致部署期间停机。

### <a name="hosting"></a>托管

整体应用程序完全承载于单个计算机实例上。 这可能需要比分布式应用程序中的任何模块都需要的功能更高的硬件。 此外，如果应用程序的任何部分成为瓶颈，则必须将整个应用程序部署到其他计算机节点，以便进行横向扩展。

### <a name="environment"></a>环境

整体应用程序通常部署在现有宿主环境（操作系统、安装的框架等）中。 此环境可能与应用程序的开发或测试环境不匹配。 应用程序环境中的不一致是单一部署问题的常见根源。

### <a name="coupling"></a>耦合

在应用程序的不同部分之间以及应用程序及其环境之间，单一应用程序可能有很大的耦合。 这可能会导致难以确定特定服务或其他问题，以便提高其可伸缩性或替换为替代实现。 此耦合还会导致对系统的更改产生更大的潜在影响，在较大的应用程序中需要大量测试。

### <a name="technology-choice"></a>技术选择

整体应用程序作为一个单元进行生成和部署。 这提供了简易性和一致性，但可能是创新的障碍。 尽管系统中的新功能或模块可能更适合于更现代的平台或框架，但很可能是使用应用程序的当前方法构建的，目的是为了实现一致性以及轻松开发和部署。

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>容器和协调器的好处是什么？

Docker 是最流行的容器管理和映像平台，可让你快速地在 Linux 和 Windows 上使用容器。 容器提供独立但可重复的应用程序环境，这些环境在任何系统上以相同的方式运行。 这使它们非常适合于在云本机应用程序中开发和承载应用程序和应用程序组件。 容器彼此隔离，因此同一主机硬件上的两个容器可以安装不同版本的软件，甚至还可以安装操作系统，而不会导致冲突。

而且，容器是通过可签入源代码管理的简单文件定义的。 与完整服务器（甚至是虚拟机）不同，通常情况下需要手动工作来应用更新或安装其他服务，容器基础结构很容易受版本控制。 因此，可使用自动工具作为生成管道的一部分来开发、测试和部署在容器中运行的应用。

容器是不可变的。 获得容器的定义后，你可以重新创建该容器，并且它将以完全相同的方式运行。 这种不可变性适用于基于组件的设计。 如果应用程序的某些部分不会像其他部分一样频繁更改，那么，当你只是部署最常更改的部件时，为什么要重新部署整个应用？ 应用的不同功能和交叉切削问题可以分解为单独的单位。 图3-2 显示了单一应用程序如何通过委托某些功能来利用容器和微服务。 应用程序本身中的其余功能也已容器化。

![打破单一应用程序，以便在后端使用微服务。](./media/breaking-up-monolith-with-backend-microservices.png)
**图 3-2**。 分解单一应用程序以在后端使用微服务。

使用单独容器构建的云本机应用会受益于根据需要部署尽可能多或更少的应用程序。 可以在节点上托管单个服务，每个服务都有相应的资源。 每个服务的运行环境是不可变的，可以在开发、测试和生产之间共享，并且可以轻松地进行版本控制。 应用程序的不同区域之间的耦合与服务间的调用或消息（而不是单体架构中的编译时依赖关系）显式发生。 整个应用程序的任何给定部分都可以选择对该功能或功能最有效的技术，无需更改应用程序的其余部分。

## <a name="what-are-the-scaling-benefits"></a>缩放的优点是什么？

基于容器构建的服务可以利用 Kubernetes 等业务流程工具提供的缩放权益。 设计容器仅知道自己的情况。 一旦开始使用多个需要协同工作的容器，就可以在更高的级别对其进行组织。 组织大量的容器及其共享依赖项（如网络配置）是业务流程工具在其中节省时间的地方！ Kubernetes 是一个容器业务流程平台，旨在自动部署、缩放和管理容器化应用程序。 它在容器组的顶层创建一个抽象层，然后将它们组织到*pod。* Pod 在称为*节点*的辅助角色计算机上运行。 整个组织组称为*群集*。 图3-3 显示了 Kubernetes 群集的不同组件。

![Kubernetes 群集组件。](./media/kubernetes-cluster-components.png)
**图 3-3**。 Kubernetes 群集组件。

Kubernetes 为满足需求的缩放群集提供内置支持。 与容器化微服务相结合，这提供了云本机应用程序，能够在需要时以及在需要时利用其他资源快速有效地响应高峰需求。

### <a name="declarative-versus-imperative"></a>声明性与命令式

Kubernetes 支持声明性和命令性对象配置。 命令式方法涉及运行各种命令，这些命令告诉 Kubernetes 如何执行每个步骤。 *运行*此映像。 *删除*此 pod。 *公开*此端口。 使用声明性方法，你可以使用描述*所需内容*的配置文件，而不是*执行哪些操作*并 Kubernetes 的内容来了解如何实现所需的结束状态。 如果已使用命令性命令配置了群集，则可以使用 `kubectl get svc SERVICENAME -o yaml > service.yaml`导出声明性清单。 这将生成如下清单文件：

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

使用声明性配置时，你可以预览将在提交之前所做的更改，方法是对配置文件所在的文件夹使用 `kubectl diff -f FOLDERNAME`。 确定要应用这些更改后，请运行 `kubectl apply -f FOLDERNAME`。 添加 `-R` 以递归方式处理文件夹层次结构。

除了服务之外，还可以对其他 Kubernetes 功能（例如*部署*）使用声明性配置。 部署控制器使用声明性部署来更新群集资源。 部署用于推出新的更改，增加以支持更多负载，或回滚到以前的修订版本。 如果群集不稳定，则声明性部署提供一种机制，用于自动将群集恢复到所需状态。

使用声明性配置，可将基础结构表示为可签入并在应用程序代码中进行版本控制的代码。 这为使用绑定到源代码管理更改的生成和部署管道提供了改进的更改控制和更好的支持。

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>哪些方案适用于容器和协调器？

以下方案非常适合使用容器和协调器。

### <a name="applications-requiring-high-uptime-and-scalability"></a>需要高运行时间和可伸缩性的应用程序

具有高运行时间和伸缩性要求的单个应用程序是使用微服务、容器和协调器的云本机体系结构的理想选择。 可以在使用版本控制环境的容器中开发这些应用程序，可以在投入生产之前对其进行广泛的测试，并可以在不停机的情况下部署到生产环境。 使用 Kubernetes 群集可确保这样的应用程序也可以按需缩放，并从节点故障中自动恢复。

### <a name="large-numbers-of-applications"></a>大量应用程序

部署和必须随后维护大量应用程序的组织可从容器和协调器中获益。 设置容器化环境和 Kubernetes 群集的前期工作主要是一项固定成本。 部署、维护和更新单个应用程序的成本与必须维护的应用程序的数量不同。 除了一定数量的应用程序之外，手动维护自定义应用程序的复杂性超出了使用容器和协调器实现解决方案的成本。

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>何时应避免使用容器和协调器？

如果你不愿意或无法按照十二因素应用程序原则构建应用程序，则可能会更好地避免容器和协调器。 在这种情况下，最好前进到基于 VM 的托管平台，或者可能是某个混合系统，你可以在其中将某些功能关闭为单独的容器，甚至无服务器功能。

## <a name="development-resources"></a>开发资源

本部分显示了可帮助你开始使用容器和协调器作为下一个应用程序的开发资源的简短列表。 如果正在寻找有关如何设计云本机微服务体系结构应用的指南，请阅读此书籍的随附 .net[微服务：容器化 .Net 应用程序的体系结构](https://aka.ms/microservicesebook)。

### <a name="local-kubernetes-development"></a>本地 Kubernetes 开发

Kubernetes 部署在生产环境中提供了极大价值，但你也可以在本地运行它们。 尽管很多时候都能独立处理单独的应用程序或微服务，但有时最好能够在本地运行整个系统，就像部署到生产环境时运行的完全一样。 有多种方法可实现此目的，其中两个是 Minikube 和 Docker 桌面。 Visual Studio 还提供了用于 Docker 开发的工具。

### <a name="minikube"></a>Minikube

什么是 Minikube？ Minikube 项目显示 "Minikube 在 macOS、Linux 和 Windows 上实现本地 Kubernetes 群集"。 它的主要目标是 "成为本地 Kubernetes 应用程序开发的最佳工具，并支持所有适合的 Kubernetes 功能"。 安装 Minikube 与 Docker 分离，但 Minikube 支持不同于 Docker Desktop 支持的虚拟机监控程序。 Minikube 目前支持以下 Kubernetes 功能：

- DNS
- NodePorts
- ConfigMaps 和机密
- 仪表板
- 容器运行时： Docker、rkt、CRI 和 containerd
- 启用容器网络接口（CNI）
- 传入

安装 Minikube 后，可以通过运行 `minikube start` 命令快速开始使用它，该命令会下载映像并启动本地 Kubernetes 群集。 启动群集后，使用标准的 Kubernetes `kubectl` 命令与该群集进行交互。

### <a name="docker-desktop"></a>Docker 桌面

你还可以直接从 Windows 上的 Docker Desktop 使用 Kubernetes。 如果你使用的是 Windows 容器，则这是你的唯一选择，对于非 Windows 容器也是不错的选择。 标准 Docker 桌面配置应用用于配置从 Docker Desktop 运行的 Kubernetes。

![在 Docker Desktop 中配置 Kubernetes](./media/docker-desktop-kubernetes.png)

**图 3-4**。 在 Docker Desktop 中配置 Kubernetes。

Docker Desktop 已经是用于本地配置和运行容器化应用程序的最受欢迎的工具。 使用 Docker Desktop 时，可以针对将部署到生产环境中的一组 Docker 容器映像进行本地开发。 Docker Desktop 设计为在本地生成、测试和交付容器化应用。 将映像发送到映像注册表（如 Azure 容器注册表或 Docker 中心）后，Azure Kubernetes Service （AKS）等服务将在生产环境中管理应用程序。

### <a name="visual-studio-docker-tooling"></a>Visual Studio Docker 工具

Visual Studio 支持对 web 应用程序进行 Docker 开发。 创建新的 ASP.NET Core 应用程序时，可以选择在项目创建过程中将其配置为 Docker 支持，如图3-5 所示。

![Visual Studio 启用 Docker 支持](./media/visual-studio-enable-docker-support.png)

**图 3-5**。 Visual Studio 启用 Docker 支持

如果选择此选项，则将使用其根中的 `Dockerfile` 创建项目，该项目可用于在 Docker 容器中生成和托管应用。 图3-6 显示了一个示例 Dockerfile。

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

**图 3-6**。 Visual Studio 生成的 Dockerfile

应用运行时的默认行为也配置为使用 Docker。 图3-7 显示了在添加 Docker 支持创建的新 ASP.NET Core 项目中可用的不同运行选项。

![Visual Studio Docker 运行选项](./media/visual-studio-docker-run-options.png)

**图 3-7**。 Visual Studio Docker 运行选项

除了本地开发外， [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/)为多个开发人员提供了一种方便的方法，以便在 Azure 中使用自己的 Kubernetes 配置。 如图3-7 所示，还可以在 Azure Dev Spaces 中运行该应用程序。

如果你在创建 ASP.NET Core 应用程序时未将 Docker 支持添加到该应用程序，则可以在以后随时添加它。 在 Visual Studio 解决方案资源管理器中，右键单击项目并选择 "**添加** > **Docker 支持**"，如图3-8 所示。

![Visual Studio 添加 Docker 支持](./media/visual-studio-add-docker-support.png)

**图 3-8**。 Visual Studio 添加 Docker 支持

除了 Docker 支持外，还可以添加容器业务流程支持，如图3-8 所示。 默认情况下，orchestrator 将使用 Kubernetes 和 Helm。 选择 orchestrator 后，会将一个 `azds.yaml` 文件添加到项目根目录中，并添加一个 `charts` 文件夹，其中包含用于配置应用程序并将其部署到 Kubernetes 的 Helm 图表。 图3-9 显示新项目中生成的文件。

![Visual Studio 添加 Orchestrator 支持](./media/visual-studio-add-orchestrator-support.png)

**图 3-9**。 Visual Studio 添加 Orchestrator 支持

## <a name="references"></a>参考

- [什么是 Kubernetes？](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [通过 Minikube 安装 Kubernetes](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube vs Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools for Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[上一页](scale-applications.md)
>[下一页](leverage-serverless-functions.md)
