---
title: 构建作为 Linux 容器部署到 AKS/Kubernetes 群集中的 ASP.NET Core 2.2 应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.date: 02/25/2019
ms.openlocfilehash: 89843e0041c12f001f974360da2e5903499155d1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644786"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>构建作为 Linux 容器部署到 AKS/Kubernetes 业务流程协调程序中的 ASP.NET Core 2.2 应用程序

Azure Kubernetes 服务 (AKS) 是 Azure 的托管 Kubernetes 业务流程服务，可简化容器部署和管理。

AKS 主要功能如下：

- Azure 托管的控制面板
- 自动升级
- 自我修复
- 用户可配置缩放
- 针对开发人员和群集操作员提供的更简单的用户体验。

以下示例探讨了如何创建在 Linux 上运行并部署到 Azure 中的 AKS 群集的 ASP.NET Core 2.2 应用程序，同时使用 Visual Studio 2017 完成开发。

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a>使用 Visual Studio 2017 创建 ASP.NET Core 2.2 项目

ASP.NET Core 是一个通用开发平台，由 Microsoft 和 GitHub 上的 .NET 社区共同维护。 它跨平台支持 Windows、macOS 和 Linux，并且可用于设备、云和嵌入式/IoT 方案。

此示例使用基于 Visual Studio Web API 模板的简单项目，因此你无需任何其他知识即可创建示例。 只需使用标准模板创建项目，该模板包含使用 ASP.NET Core 2.2 技术运行带有 REST API 的小项目的所有元素。

![Visual Studio 中的“添加新项目”窗口，已选择 ASP.NET Core Web 应用。](media/create-aspnet-core-application.png)

图 4-36  . 创建 ASP.NET Core 应用程序

要在 Visual Studio 中创建示例项目，请选择“文件” > “新建” > “项目”，选择左侧窗格中的“Web”项目类型，再选择“ASP.NET Core Web 应用”      。

Visual Studio 列出了 Web 项目的模板。 对于本示例，请选择“API”以创建 ASP.NET Web API 应用程序  。

验证是否已选择 ASP.NET Core 2.2 作为框架。 .NET Core 2.2 包含在 Visual Studio 2017 的最新版本中，并在安装 Visual Studio 2017 时自动安装和配置。

![用于选择 ASP.NET Core Web 应用类型的 Visual Studio 对话框，已选择 API 选项。](media/create-web-api-application.png)

图 4-37  . 选择 ASP.NET Core 2.2 和 Web API 项目类型

如果有任何以前版本的 .NET Core，则可以从 <https://www.microsoft.com/net/download/core#/sdk> 下载并安装 2.2 版本。

可以在创建项目时或之后添加 Docker 支持，以便能够随时“Docker 化”项目。 若要在创建项目后添加 Docker 支持，请在解决方案资源管理器中右键单击项目节点，然后在上下文菜单中选择“添加” > “Docker 支持”   。

![用于向现有项目添加 Docker 支持的上下文菜单选项：右键单击（在项目上）>“添加”>“Docker 支持”。](media/add-docker-support-to-project.png)

图 4-38  . 向现有项目添加 Docker 支持

若要完成添加 Docker 支持，可以选择 Windows 或 Linux。 在此情况下，选择“Linux”，因为 AKS 不支持 Windows 容器（自 2018 年末起）  。

![为 Dockerfile 选择目标操作系统的选项对话框。](media/select-linux-docker-support.png)

图 4-39  . 选择 Linux 容器。

你已使用这些简单步骤在 Linux 容器上运行 ASP.NET Core 2.2 应用程序。

如你所见，Visual Studio 2017 与 Docker 之间的集成完全面向开发人员的工作效率。

现在，可以使用“F5”键或使用“开始”按钮运行应用程序   。

运行项目后，可以使用 `docker images` 命令列出映像。 应看到使用 Visual Studio 2017 自动部署项目所创建的 `mssampleapplication` 映像。

```console
docker images
```

![来自 Docker 映像命令的控制台输出，显示了一个包含以下内容的列表：存储库、标记、映像 ID、创建（日期）和大小。](media/docker-images-command.png)

图 4-40  . Docker 映像视图

## <a name="register-the-solution-in-the-azure-container-registry"></a>在 Azure 容器注册表中注册解决方案

将映像上传到任何 Docker 注册表，如 [Azure 容器注册表 (ACR)](https://azure.microsoft.com/services/container-registry/) 或 Docker Hub，以便能够从该注册表将映像部署到 AKS 群集。 在此情况下，我们将映像上传到 Azure 容器注册表。

### <a name="create-the-image-in-release-mode"></a>在发布模式下创建映像

现在，我们将通过更改为“发布”，在“发布”模式（准备生产）中创建映像，如图 4-41 所示，并像以前一样运行应用程序   。

![VS 中的工具栏选项，用于在发布模式下生成。](media/select-release-mode.png)

图 4-41  . 选择发布模式

如果执行 `docker image` 命令，将看到已创建两个映像，一个用于 `debug` 模式，另一个用于 `release` 模式。

### <a name="create-a-new-tag-for-the-image"></a>为映像创建新标记

需要使用注册表的 `loginServer` 名称标记每个容器映像。 在将容器映像推送到映像注册表时，使用此标记进行路由。

可以从 Azure 门户中查看 `loginServer` 名称，从 Azure 容器注册表中获取信息

![位于右上角的 Azure 容器注册表名称的浏览器视图。](media/loginServer-name.png)

图 4-42  . 注册表名称的视图

或者通过运行以下命令：

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![来自上述命令的控制台输出。](media/az-cli-loginServer-name.png)

图 4-43  . 使用 PowerShell 获取注册表的名称

这两种情况都可获得名称。 在本示例中，为 `mssampleacr.azurecr.io`。

现在，可以使用以下命令标记映像，获取最新映像（发布映像）：

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

运行 `docker tag` 命令后，使用 `docker images` 命令列出映像，你应看到带有新标记的映像。

![来自 Docker 映像命令的控制台输出。](media/tagged-docker-images-list.png)

图 4-44  . 带标记的映像视图

### <a name="push-the-image-into-the-azure-acr"></a>将映像推送到 Azure ACR

登录到 Azure 容器注册表

```console
az acr login --name mssampleacr
```

使用以下命令将映像推送到 Azure ACR：

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

此命令需要一段时间上传映像，但会在此过程中为你提供反馈。

![来自 Docker 推送命令的控制台输出：显示每个层的基于字符的进度栏。](media/uploading-image-to-acr.png)

图 4-45  . 将映像上传到 ACR

可以在下面看到流程完成时应获得的结果：

![来自 Docker 推送命令的已完成的控制台输出，显示了所有层或节点。](media/uploading-docker-images-complete.png)

图 4-46  . 节点视图

下一步是将容器部署到 AKS Kubernetes 群集中。 为此，需要一个包含以下内容的文件（.yml 部署文件）  ：

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - name: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> 有关使用 Kubernetes 进行部署的更多信息，请参阅：<https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

现已准备好使用 Kubectl 进行部署，但首先必须使用以下命令获取 AKS 群集的凭据  ：

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![来自上述命令的控制台输出：Merged "MSSampleK8Cluster as current context in  /root/.kube/config](media/getting-aks-credentials.png)

图 4-47  . 获取凭据

然后，使用 `kubectl create` 命令启动部署。

```console
kubectl create -f mssample-deploy.yml
```

![来自上述命令的控制台输出：已创建部署“mssamplesbook”。 已创建服务“mssample-kub-app”。](media/kubectl-create-command.png)

图 4-48  . 部署到 Kubernetes

部署完成后，可以使用可使用以下命令暂时访问的本地代理访问 Kubernetes 控制台：

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

并访问 url `http://127.0.0.1:8001`。

![Kubernetes 仪表板的浏览器视图，显示了部署、Pod、副本集和服务。](media/kubernetes-cluster-information.png)

图 4-49  . 查看 Kubernetes 群集信息

现在，你已使用 Linux 容器和 AKS Kubernetes 群集在 Azure 上部署应用程序。 可访问应用，浏览到可从 Azure 门户获取的服务的公共 IP。

> [!NOTE]
> 可在本指南的[部署到 Azure Kubernetes 服务 (AKS)](deploy-azure-kubernetes-service.md) 部分中了解如何为此示例创建 AKS 群集  。

>[!div class="step-by-step"]
>[上一页](set-up-windows-containers-with-powershell.md)
>[下一页](../docker-devops-workflow/index.md)
