---
title: 为 WCF 开发人员提供 Docker - gRPC
description: 为ASP.NET核心 gRPC 应用程序创建 Docker 映像
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148109"
---
# <a name="create-docker-images"></a>创建 Docker 映像

本节介绍为ASP.NET Core gRPC 应用程序创建 Docker 映像，这些应用程序可在 Docker、Kubernetes 或其他容器环境中运行。 使用的示例应用程序，带有ASP.NET酷睿 MVC Web 应用和 gRPC 服务，可在 GitHub 上的[dotnet 架构/grpc-for wcf 开发人员](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)存储库中使用。

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>用于ASP.NET核心应用程序的微软基本映像

Microsoft 为构建和运行 .NET Core 应用程序提供了一系列基本映像。 要创建 ASP.NET酷睿 3.0 图像，请使用两个基本映像：

- 用于生成和发布应用程序的 SDK 映像。
- 用于部署的运行时映像。

| 映像 | 说明 |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | 用于使用`docker build`生成应用程序。 不用于生产。 |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | 包含运行时和 ASP.NET核心依赖项。 用于生产。 |

对于每个映像，有四种基于不同 Linux 发行版的变体，按标记区分。

| 图像标记 | Linux | 说明 |
| --------- | ----- | ----- |
| 3.0-破坏者，3.0 | Debian 10 | 如果未指定操作系统变体，则默认映像。 |
| 3.0-高山 | 阿尔卑斯 3.9 | 阿尔卑斯基图图像比Debian或Ubuntu图像小得多。 |
| 3.0-迪斯科 | Ubuntu 19.04 | |
| 3.0-仿生 | Ubuntu 18.04 | |

阿尔卑斯基图约为 100 MB，而 Debian 和 Ubuntu 图像的映像为 200 MB。 某些软件包或库在 Alpine 的软件包管理中可能不可用。 如果您不确定要使用的图像，则可能需要选择默认的 Debian。

> [!IMPORTANT]
> 请确保在生成和运行时使用相同的 Linux 变体。 在一个变体上构建和发布的应用程序可能不适用于另一个变体。

## <a name="create-a-docker-image"></a>创建 Docker 映像

Docker 映像由 Docker*文件*定义。 这是一个文本文件，其中包含生成应用程序和安装生成或运行应用程序所需的任何依赖项所需的所有命令。 下面的示例显示了 ASP.NET Core 3.0 应用程序的最简单的 Dockerfile：

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Dockerfile 有两个部分：第一部分使用`sdk`基本映像来构建和发布应用程序;第二部分使用基本映像来构建和发布应用程序。第二个从基中`aspnet`创建运行时映像。 这是因为`sdk`映像约为 900 MB，而运行时映像的映像约为 200 MB，并且大多数内容在运行时是不必要的。

### <a name="the-build-steps"></a>生成步骤

| 步骤 | 说明 |
| ---- | ----------- |
| `FROM ...` | 声明基本映像并分配`builder`别名。 |
| `WORKDIR /src` | 创建`/src`目录并将其设置为当前工作目录。 |
| `COPY . .` | 将主机上当前目录下的所有内容复制到映像上的当前目录中。 |
| `RUN dotnet restore` | 还原任何外部包（ASP.NET与 SDK 一起预安装核心 3.0 框架）。 |
| `RUN dotnet publish ...` | 生成和发布发布版本。 请注意，`--runtime`该标志不是必需的。 |

### <a name="the-runtime-image-steps"></a>运行时映像步骤

| 步骤 | 说明 |
| ---- | ----------- |
| `FROM ...` | 声明新的基本映像。 |
| `WORKDIR /app` | 创建`/app`目录并将其设置为当前工作目录。 |
| `COPY --from=builder ...` | 使用第一`builder``FROM`行中的别名从上一个图像复制已发布的应用程序。 |
| `ENTRYPOINT [ ... ]` | 将命令设置在容器启动时运行。 运行时`dotnet`映像中的命令只能运行 DLL 文件。 |

### <a name="https-in-docker"></a>Docker 中的 HTTPS

Docker 的 Microsoft 基本`ASPNETCORE_URLS`映像将环境`http://+:80`变量设置为 ，这意味着 Kestrel 在该端口上运行没有 HTTPS。 如果将 HTTPS 与自定义证书一起使用（如[自托管 gRPC 应用程序中](self-hosted.md)所述），则应重写此证书。 在 Dockerfile 的运行时映像创建部分设置环境变量。

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>.dockerignore 文件

与从`.gitignore`源代码管理中排除某些文件和目录的文件类似，`.dockerignore`该文件可用于在生成期间将文件和目录复制到映像。 这不仅节省了复制时间，还可以避免将 PC 中的`obj`目录复制到映像中出现的一些错误。 至少，应为`bin`文件添加条目，并`obj`添加到文件中`.dockerignore`。

```console
bin/
obj/
```

## <a name="build-the-image"></a>生成映像

对于具有单个应用程序的解决方案，以及单个 Dockerfile，将 Dockerfile 放在基本目录中是最简单的。 换句话说，将其放在与`.sln`文件相同的目录中。 在这种情况下，要生成映像，请使用包含 Dockerfile`docker build`的目录中的以下命令。

```console
docker build --tag stockdata .
```

令人困惑的名称`--tag`标志（可以缩短为`-t`）指定图像的整个名称，包括指定的实际标记。 `.`末尾指定将在其中运行生成的上下文;Docker 文件中命令的`COPY`当前工作目录。

如果单个解决方案中有多个应用程序，则可以将每个应用程序的 Dockerfile 保留在文件旁边的`.csproj`自己的文件夹中。 您仍应从基`docker build`目录中运行该命令，以确保将解决方案和所有项目复制到映像中。 可以使用`--file`（ 或`-f`） 标志在当前目录下方指定 Docker 文件。

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>在计算机上的容器中运行映像

要在本地 Docker 实例中运行映像，请使用`docker run`命令。

```console
docker run -ti -p 5000:80 stockdata
```

标志`-ti`将当前终端连接到容器的终端，并在交互式模式下运行。 容器`-p 5000:80`上的发布（链接）端口 80 到本地主机网络接口上的端口 5000。

## <a name="push-the-image-to-a-registry"></a>将映像推送到注册表

验证映像是否正常工作后，将其推送到 Docker 注册表，使其在其他系统上可用。 内部网络将需要预配 Docker 注册表。 这可以像运行[Docker 自己的`registry`映像](https://docs.docker.com/registry/deploying/)（Docker 注册表在 Docker 容器中运行）一样简单，但有多种更全面的解决方案可用。 对于外部共享和云使用，可以使用各种托管注册表，例如[Azure 容器注册表](https://docs.microsoft.com/azure/container-registry/)或[Docker Hub。](https://docs.docker.com/docker-hub/repos/)

要推送到 Docker 中心，请用用户或组织名称对图像名称进行前缀。

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

要推送到专用注册表，使用注册表主机名和组织名称对映像名称进行前缀。

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

映像在注册表中后，您可以将其部署到单独的 Docker 主机，或部署到容器编排引擎（如 Kubernetes）。

>[!div class="step-by-step"]
>[上一个](self-hosted.md)
>[下一个](kubernetes.md)
