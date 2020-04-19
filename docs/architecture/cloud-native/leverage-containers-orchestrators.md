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
# <a name="leveraging-containers-and-orchestrators"></a>利用容器和协调器

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

容器和协调器旨在解决单一部署方法中常见的问题。

## <a name="challenges-with-monolithic-deployments"></a>整体部署的挑战

传统上，大多数应用程序都部署为单个单元。 此类应用程序称为单体。 这种将应用程序部署为单个单元的一般方法，即使它们由多个模块或程序集组成，也称为单片架构，如图 3-1 所示。

![单体架构。](./media/monolithic-architecture.png)

**图3-1**。 单体架构。

尽管单片式架构具有简单性的优点，但它们面临着许多挑战：

### <a name="deployments"></a>部署

部署到单一应用程序通常需要重新启动整个应用程序，即使只替换一个小型模块也是如此。 根据托管应用程序的计算机数，这可能导致部署期间的停机时间。

### <a name="hosting"></a>Hosting

单片应用程序完全托管在单个计算机实例上。 这可能需要比分布式应用程序中任何模块所需的更高功能的硬件。 此外，如果应用的任何部分成为瓶颈，则必须将整个应用程序部署到其他计算机节点才能横向扩展。

### <a name="environment"></a>环境

单片应用程序通常部署到现有的托管环境（操作系统、已安装的框架等）。 此环境可能与开发或测试应用程序的环境不匹配。 应用程序环境中的不一致是单一部署的常见问题来源。

### <a name="coupling"></a>耦合

单片应用程序在应用程序的不同部分之间以及应用程序与其环境之间可能有很大的耦合。 这会使以后难以分解特定服务或问题，以便增加其可伸缩性或在替代实现中交换。 这种耦合还会导致对系统更改产生更大的潜在影响，需要在较大的应用中进行广泛的测试。

### <a name="technology-choice"></a>技术选择

单片应用程序作为一个单元构建和部署。 这提供了简单性和统一性，但可能是创新的障碍。 尽管系统中的新功能或模块可能更适合更现代的平台或框架，但为了一致性以及易于开发和部署，可能会使用应用程序的当前方法构建它。

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>容器和协调器有什么好处？

Docker 是最受欢迎的容器管理和映像平台，允许您快速处理 Linux 和 Windows 上的容器。 容器提供单独但可重现的应用程序环境，这些环境在任何系统上以相同的方式运行。 这使得它们非常适合在云原生应用程序中开发和托管应用程序和应用程序组件。 容器彼此隔离，因此同一主机硬件上的两个容器可以安装不同版本的软件，甚至操作系统，而不会造成依赖项冲突。

此外，容器由可签入源代码管理的简单文件定义。 与完整服务器（甚至虚拟机）不同，通常需要手动工作才能应用更新或安装其他服务，因此容器基础结构很容易被版本控制。 因此，在容器中运行构建的应用可以使用自动工具作为生成管道的一部分进行开发、测试和部署。

容器是不可改变的。 获得容器的定义后，可以重新创建该容器，并且它将以完全相同的方式运行。 这种不变性适用于基于组件的设计。 如果应用程序的某些部分更改频率不如其他部分频繁，那么为什么当您只需部署更改次数最多的部分时，才能重新部署整个应用程序？ 应用的不同功能和交叉问题可以分解为单独的单元。 图 3-2 显示了单片应用如何通过委派某些功能或功能来利用容器和微服务。 应用本身的剩余功能也已容器化。

![分解单片应用，在后端使用微服务。](./media/breaking-up-monolith-with-backend-microservices.png)
**图3-2**. 分解单片应用，在后端使用微服务。

使用单独的容器构建的云原生应用可根据需要部署尽可能多的或很少的应用程序。 单个服务可以托管在具有适合每个服务的节点上。 每个服务运行的环境是不可变的，可以在开发、测试和生产之间共享，并且可以轻松进行版本控制。 应用程序不同区域之间的耦合作为服务之间的调用或消息显式发生，而不是单体中的编译时间依赖项。 整个应用的任何给定部分都可以选择对该功能或功能最有意义的技术，而无需更改应用的其余部分。

## <a name="what-are-the-scaling-benefits"></a>扩展优势是什么？

构建在容器上的服务可以利用库伯奈斯等业务流程工具提供的扩展优势。 根据设计，容器只知道自己。 一旦开始有多个容器需要协同工作，就可以在更高的级别组织它们。 组织大量容器及其共享依赖项（如网络配置）是业务流程工具用于节省一天的位置！ Kubernetes 是一个容器编排平台，旨在自动部署、扩展和管理容器化应用程序。 它在容器组之上创建一个抽象层，并将它们组织到*窗格中*。 在称为*节点*的工作计算机上运行的 Pod。 整个有组织的组称为*群集*。 图 3-3 显示了库伯内斯群集的不同组件。

![库伯内斯集群组件。](./media/kubernetes-cluster-components.png)
**图3-3**. 库伯内斯集群组件。

Kubernetes 内置支持扩展群集以满足需求。 结合容器化微服务，这为云原生应用程序提供了在需要时和任何地方使用额外资源快速高效地响应需求高峰的能力。

### <a name="declarative-versus-imperative"></a>声明性与命令性

库伯内斯支持声明性对象和命令性对象配置。 命令性方法涉及运行各种命令，告诉 Kubernetes 如何执行每一步。 *运行*此映像。 *删除*此窗格。 *公开*此端口。 使用声明性方法，您可以使用一个配置文件来描述*您想要做什么*而不是*做什么*，Kubernetes 会找出要做什么来实现所需的结束状态。 如果已经使用命令命令配置群集，则可以使用 导出声明性清单`kubectl get svc SERVICENAME -o yaml > service.yaml`。 这将生成如下所示的清单文件：

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

使用声明性配置时，可以通过对配置文件所在的文件夹进行引用`kubectl diff -f FOLDERNAME`之前预览这些更改。 确定要应用更改后，请运行`kubectl apply -f FOLDERNAME`。 添加到`-R`递归处理文件夹层次结构。

除了服务之外，还可以对其他 Kubernetes 功能（如*部署*）使用声明性配置。 声明性部署由部署控制器用于更新群集资源。 部署用于添加新更改、向上扩展以支持更多负载或回滚到以前的修订版。 如果群集不稳定，声明性部署提供了自动将群集恢复到所需状态的机制。

使用声明性配置可以将基础结构表示为代码，该代码可以签入并随着应用程序代码进行版本控制。 这提供了改进的更改控制，并更好地支持使用与源代码管理更改关联的生成和部署管道进行持续部署。

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>哪些方案非常适合容器和协调器？

以下方案非常适合使用容器和协调器。

### <a name="applications-requiring-high-uptime-and-scalability"></a>需要高停机时间和可扩展性的应用程序

具有高高高高高高高扩展性和可扩展性要求的各个应用程序是使用微服务、容器和协调器的云原生体系结构的理想选择。 这些应用程序可以使用版本化环境在容器中开发，可以在生产前进行广泛测试，并且可以以零停机时间部署到生产中。 使用 Kubernetes 群集可确保此类应用还可以按需扩展，并从节点故障中自动恢复。

### <a name="large-numbers-of-applications"></a>大量应用

部署并随后必须维护大量应用程序的组织受益于容器和协调器。 设置容器化环境和 Kubernetes 群集的前期工作主要是固定成本。 部署、维护和更新单个应用程序的成本随必须维护的应用程序数量而异。 除了数量相当少的应用程序之外，手动维护自定义应用程序的复杂性超过了使用容器和协调器实现解决方案的成本。

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>何时应避免使用容器和协调器？

如果您不愿意或无法按照十二因子应用原则构建应用程序，则最好避免容器和协调器。 在这些情况下，最好使用基于 VM 的托管平台，或者可能采用一些混合系统，您可以在其中将某些功能引入单独的容器甚至无服务器功能。

## <a name="development-resources"></a>开发资源

本节显示一个开发资源的简短列表，这些资源可帮助您开始为下一个应用程序使用容器和协调器。 如果您正在寻找有关如何设计云原生微服务体系结构应用的指导，请阅读本书的配套书[.NET 微服务：容器化 .NET 应用程序的体系结构](https://aka.ms/microservicesebook)。

### <a name="local-kubernetes-development"></a>当地库伯内斯开发

Kubernetes 部署在生产环境中提供了巨大的价值，但您也可以在本地运行它们。 尽管大部分时间都能够独立处理单个应用或微服务是件好事，但有时能够像部署到生产时一样在本地运行整个系统是件好事。 有几种方法可以实现此目的，其中两种方法是 Minikube 和 Docker 桌面。 Visual Studio 还为 Docker 开发提供工具。

### <a name="minikube"></a>Minikube

什么是米尼库贝？ Minikube 项目说："Minikube 在 macOS、Linux 和 Windows 上实现了本地 Kubernetes 群集。 其主要目标是"成为本地Kubernetes应用程序开发的最佳工具，并支持所有适合的Kubernetes功能。 安装 Minikube 与 Docker 是分开的，但 Minikube 支持与 Docker 桌面支持不同的虚拟机管理程序。 Minikube 目前支持以下库伯奈斯功能：

- DNS
- 节点端口
- 配置映射和机密
- 仪表板
- 容器运行时：码头、rkt、CRI-O 和容器
- 启用容器网络接口 （CNI）
- 流入量

安装 Minikube 后，可以通过运行`minikube start`命令快速开始使用它，该命令下载映像并启动本地 Kubernetes 群集。 群集启动后，您将使用标准的 Kubernetes`kubectl`命令与其交互。

### <a name="docker-desktop"></a>Docker Desktop

您还可以直接从 Windows 上的 Docker 桌面使用 Kubernetes。 如果您使用的是 Windows 容器，这是您唯一的选择，也是非 Windows 容器的绝佳选择。 标准 Docker 桌面配置应用用于配置从 Docker 桌面运行的库伯内特。

![在 Docker 桌面中配置库伯内斯](./media/docker-desktop-kubernetes.png)

**图3-4**。 在 Docker 桌面中配置库伯内斯。

Docker 桌面已经是本地配置和运行容器化应用的最常见工具。 使用 Docker Desktop 时，可以针对要部署到生产的完全相同的 Docker 容器映像集在本地进行开发。 Docker 桌面旨在"在本地构建、测试和发货"容器化应用。 将映像发送到映像注册表（如 Azure 容器注册表或 Docker Hub）后，Azure Kubernetes 服务 （AKS） 等服务将管理生产中的应用程序。

### <a name="visual-studio-docker-tooling"></a>视觉工作室码头工具

Visual Studio 支持 Web 应用程序的 Docker 开发。 创建新的ASP.NET核心应用程序时，您可以选择使用 Docker 支持来配置该应用程序，作为项目创建过程的一部分，如图 3-5 所示。

![可视化工作室启用 Docker 支持](./media/visual-studio-enable-docker-support.png)

**图3-5**。 可视化工作室启用 Docker 支持

选择此选项后，将使用 root 中的 项目`Dockerfile`创建项目，可用于在 Docker 容器中生成和托管应用。 如图 3-6 所示有一个示例 Dockerfile。

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

**图3-6**. 可视化工作室生成的 Dockerfile

应用运行时的默认行为也配置为使用 Docker。 图 3-7 显示了添加了 Docker 支持后创建的新ASP.NET核心项目中可用的不同运行选项。

![可视化工作室 Docker 运行选项](./media/visual-studio-docker-run-options.png)

**图3-7**。 可视化工作室 Docker 运行选项

除了本地开发之外[，Azure 开发人员空间](https://docs.microsoft.com/azure/dev-spaces/)还为多个开发人员提供了一种在 Azure 中处理其自己的 Kubernets 配置的便捷方法。 如图 3-7 所示，您还可以在 Azure 开发空间中运行应用程序。

如果在创建 ASP.NET 酷应用程序时未将 Docker 支持添加到该应用程序，则始终可以在以后添加它。 在可视化工作室解决方案资源管理器中，右键单击项目并选择 **"添加** > **Docker 支持**"，如图 3-8 所示。

![可视化工作室添加 Docker 支持](./media/visual-studio-add-docker-support.png)

**图3-8**。 可视化工作室添加 Docker 支持

除了 Docker 支持之外，您还可以添加容器业务流程支持，如图 3-8 所示。 默认情况下，协调器使用库伯奈斯和赫尔姆。 选择协调器后，将`azds.yaml`文件添加到项目根，并添加一个`charts`文件夹，其中包含用于配置应用程序并将应用程序部署到 Kubernetes 的 Helm 图表。 图 3-9 显示了新项目中生成的文件。

![可视化工作室添加协调器支持](./media/visual-studio-add-orchestrator-support.png)

**图3-9**. 可视化工作室添加协调器支持

## <a name="references"></a>参考

- [什么是 Kubernetes？](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [安装库伯内斯与米尼库贝](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [迷你库贝 vs Docker 桌面](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools for Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[上一页](scale-applications.md)
>[下一页](leverage-serverless-functions.md)
