---
title: "Docker 应用开发工作流"
description: "用于容器化 .NET 应用程序的 .NET 微服务体系结构 | Docker 应用开发工作流"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a0f20e5b568a464b5c860e3da51e52d4f7d79972
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="development-workflow-for-docker-apps"></a>Docker 应用开发工作流

应用程序开发生命周期从每位开发人员的计算机上开始，开发人员在计算机上使用其首选语言对应用程序进行编码和本地测试。 无论选择哪种语言、框架和平台，采用本工作流后，开发人员始终要开发和测试 Docker 容器，但在本地进行操作即可。

每个容器（Docker 映像的实例）都包含以下组成部分：

-   选择的操作系统（例如，Linux 发行版、Windows Nano Server 或 Windows Server Core）。

-   开发人员添加的文件（应用程序二进制文件等）。

-   配置信息（环境设置和依赖项）。

## <a name="workflow-for-developing-docker-container-based-applications"></a>开发基于 Docker 容器的应用程序的工作流

本节介绍基于 Docker 容器的应用程序的内部循环开发工作流。 内部循环工作流是指不考虑更广泛的 DevOps 工作流，只关注在开发人员的计算机上进行的开发工作。 其中不包括设置环境的初始步骤，因为这些步骤只需进行一次。

应用程序由开发人员自己的服务和附加库（依赖项）组成。 以下是生成 Docker 应用程序时常用的基本步骤，如图 5-1 所示。

![](./media/image1.png)

**图 5-1**。 开发 Docker 容器化应用的分步工作流

本指南详细介绍了整个流程，并着重通过 Visual Studio 环境解释了每个主要步骤。

使用编辑器/CLI 开发方法（例如，Visual Studio Code 和 macOS 或 Windows 上的 Docker CLI）时，需了解每个步骤，通常需要比使用 Visual Studio 了解得更详细。 有关在 CLI 环境中进行开发的详细信息，请参阅电子书 [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/)（容器化 Docker 应用程序生命周期与 Microsoft 平台和工具）。

使用 Visual Studio 2015 或 Visual Studio 2017 时，许多步骤都无需开发者执行，可显著提高工作效率。 使用 Visual Studio 2017 开发多容器应用程序时更是如此。 例如，只需单击一下，Visual Studio 就会将 Dockerfile 和 docker-compose.yml 文件添加到含有应用程序配置的项目。 在 Visual Studio 中运行应用程序时，系统会生成 Docker 映像并在 Docker 中直接运行多容器应用程序；开发人员甚至还能同时调试多个容器。 这些功能可大大提高开发速度。

但即使 Visual Studio 可以自动执行这些步骤，这也并不意味着开发人员不需要了解 Docker 的工作原理。 因此，接下来的内容会详细介绍每个步骤。

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>步骤 1。 开始编码并创建初始应用程序或服务基线

开发 Docker 应用程序的方式与开发不带 Docker 的应用程序的方式类似。 二者的区别在于，开发 Docker 应用程序时，是在本地环境中部署和测试在 Docker 容器中运行的应用程序或服务。 该容器可以是 Linux 容器或 Windows 容器。

### <a name="set-up-your-local-environment-with-visual-studio"></a>使用 Visual Studio 设置本地环境

首先，请务必按以下说明所述安装适用于 Windows 的 [Docker 社区版 (CE)](https://www.docker.com/community-edition)：

[Get started with Docker CE for Windows](https://docs.docker.com/docker-for-windows/)（适用于 Windows 的 Docker CE 入门）

此外还需安装 Visual Studio 2017。 Visual Studio 2015 含有 Visual Studio Tools for Docker 加载项，但推荐安装 Visual Studio 2017，因为它为 Docker 提供了更高级的支持，例如容器调试支持。 如果在安装时选择了“ .NET Core 和 Docker”工作负载，Visual Studio 2017 会包含 Docker 工具，如图 5-2 所示。

![](./media/image3.png)

**图 5-2**。 安装 Visual Studio 2017 时选择“.NET Core 和 Docker”工作负载

即使尚未在应用程序中启用 Docker，开发人员也可以开始在普通 .NET 中编写应用程序（如果打算使用容器，则通常在 .NET Core 中进行），并在 Docker 中进行部署和测试。 但建议尽快开始使用 Docker，因为这才是真实环境，并且能快速发现存在的问题。 推荐这样做是因为通过 Visual Studio 可轻松使用 Docker，开发人员能够快速明白，在 Visual Studio 中能调试多容器应用程序就是一个很好的示例。

### <a name="additional-resources"></a>其他资源

-   **Get started with Docker CE for Windows**（适用于 Windows 的 Docker CE 入门）
    [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio 2017**
    [https://www.visualstudio.com/vs/visual-studio-2017/](https://www.visualstudio.com/vs/visual-studio-2017/)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>步骤 2。 创建与现有 .NET 基础映像相关的 Dockerfile

要生成自定义映像，需为每个自定义映像提供一个 Dockerfile；无论是从 Visual Studio 自动部署，还是使用 Docker CLI（docker run 和 docker-compose 命令）手动部署，也需为每个要部署的容器提供一个 Dockerfile。 如果应用程序只包含一个自定义服务，则只需要一个 Dockerfile。 如果应用程序包含多个服务（如在微服务体系结构中），则每个服务都需要一个 Dockerfile。

将 Dockerfile 放在应用程序或服务的根文件夹中。 Dockerfile 包含多个命令，可指示 Docker 如何在容器中设置和运行应用程序或服务。 开发人员可在代码中手动创建 Dockerfile，并将其与 .NET 依赖项一起添加到项目中。

借助 Visual Studio 及其 Docker 工具，只需单击几次鼠标即可完成此任务。 在 Visual Studio 2017 中新建项目时，会有一个名为“启用容器 (Docker) 支持”的选项，如图 5-3 所示。

![](./media/image5.png)

**图 5-3**。 在 Visual Studio 2017 中新建项目时的“启用 Docker 支持”

还可通过在 Visual Studio 中右键单击项目文件，选择“添加 Docker 项目支持”选项，为新项目或现有项目启用 Docker 支持，如图 5-4 所示。

![](./media/image6.png)

**图 5-4**。 在现有 Visual Studio 2017 项目中启用 Docker 支持

对项目（如 ASP.NET Web 应用程序或 Web API 服务）应用此操作后，系统会向含有所需配置的项目添加 Dockerfile。 同时还会向整个解决方案添加 docker-compose.yml 文件。 接下来将介绍每个文件中包含的信息。 Visual Studio 可代为执行此操作，但了解 Dockerfile 中的内容也十分有用。

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>选项 A：使用现有的官方 .NET Docker 映像创建项目

开发人员通常以基础映像（可从 [Docker 中心](https://hub.docker.com/)注册表的官方存储库中获取）为基础生成自定义映像。 确切地说，在 Visual Studio 中启用 Docker 支持后就可以执行此操作。 Dockerfile 将使用现有的 aspnetcore 映像。

之前我们介绍了根据开发人员选择的框架和操作系统可使用的 Docker 映像和存储库。 例如，如果想使用 ASP.NET Core（Linux 或 Windows），则使用的映像是 microsoft/aspnetcore:2.0。 因此，只需指定用于容器的基础 Docker 映像即可。 方法是将 FROM microsoft/aspnetcore:2.0 添加到 Dockerfile。 Visual Studio 会自动执行此操作，但若要更新版本，则需更新此值。

使用从 Docker 中心获取的带版本号的官方 .NET 映像存储库可确保能在所有计算机（包括用于开发、测试和生产的计算机）上使用相同的语言功能。

以下示例显示了 ASP.NET Core 容器的示例 Dockerfile。

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

此时该容器以 2.0 版官方 ASP.NET Core Docker 映像为基础（适用于 Linux 和 Windows 的多体系结构）。 这是 `FROM microsoft/aspnetcore:2.0` 设置。 （有关此基础映像的详细信息，请参阅 [ASP.NET Core Docker 映像](https://hub.docker.com/r/microsoft/aspnetcore/)页和 [.NET Core Docker 映像](https://hub.docker.com/r/microsoft/dotnet/)页。）在 Dockerfile 中，还需指示 Docker 侦听要在运行时使用的 TCP 端口（示例中由 EXPOSE 设置配置的 TPC 端口为 80）。

可在 Dockerfile 中指定其他配置设置，具体取决于使用的语言和框架。 例如，带有 \["dotnet", "MySingleContainerWebApp.dll"\] 的 ENTRYPOINT 行可指示 Docker 运行 .NET Core 应用程序。 如果使用 SDK 和 .NET Core CLI (dotnet CLI) 来生成和运行 .NET 应用程序，则此设置会有所不同。 底部的 ENTRYPOINT 行和其他设置会有所不同，具体取决于为应用程序选择的语言和平台。

### <a name="additional-resources"></a>其他资源

-   **为 .NET Core 应用程序生成 Docker 映像**
    [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)

-   **生成开发人员自己的映像**。 请查看官方 Docker 文档。
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>使用多体系结构映像存储库

单个存储库中可包含平台变量，如 Linux 映像和 Windows 映像。 借助此功能，Microsoft （基础映像创建者）等供应商可创建涵盖多个平台（即 Linux 和 Windows）的单个存储库。 例如，Docker 中心注册表中提供的 [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) 存储库可使用相同的存储库名称为 Linux 和 Windows Nano Server 提供支持。

如果指定了标签，请明确指定一个平台，如下所示：

-   **microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

但自 2017 年中旬以来，此情况出现了变化，如果指定相同的映像名称，即使使用的标记相同，新的多体系结构映像（如支持多体系结构的 aspnetcore 映像）也将使用 Linux 或 Windows 版本，具体取决于正在部署的 Docker 主机操作系统，如下所示：

-   **microsoft/aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

这样一来，从 Windows 主机拉取映像时，也会拉取 Windows 变体，并且从 Linux 主机拉取同一映像名称时，也会拉取 Linux 变体。

### <a name="option-b-creating-your-base-image-from-scratch"></a>选项 B：从头开始创建基础映像

开发人员可以从头开始创建自己的 Docker 基础映像。 不推荐刚开始使用 Docker 的开发人员使用此方案，但如果想为自己的基础映像设置特定位，则可采用此方案。

### <a name="additional-resources"></a>其他资源

-   **Multi-arch .NET Core images**（多体系结构 .NET Core 映像）。
https://github.com/dotnet/announcements/issues/14 
-   **创建基础映像**。 请查看官方 Docker 文档。
    [https://docs.docker.com/engine/userguide/eng-image/baseimages/](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>步骤 3。 创建自定义 Docker 映像并将应用程序或服务嵌入其中

需为应用程序中的每项服务创建一个相关映像。 如果应用程序由单个服务或 Web 应用程序组成，则只需创建一个映像。

请注意，Visual Studio 中会自动生成 Docker 映像。 以下步骤仅适用于编辑器/CLI 工作流，下文清楚解释了各步骤的工作原理。

开发人员发布完整功能或更改源代码管理系统（例如 GitHub）之前，需在本地进行开发和测试。 这意味着开发人员需要创建 Docker 映像并向本地 Docker 主机（Windows 或 Linux VM）部署容器，并运行、测试和调试这些本地容器。

若要使用 Docker CLI 和 Dockerfile 在本地环境中创建自定义映像，可使用 docker build 命令，如图 5-5 所示。

![](./media/image8.png)

**图 5-5**。 创建自定义 Docker 映像

（可选），可先运行 dotnet 发布生成包含所需 .NET 库和二进制文件的可部署文件夹，然后使用 docker build 命令，而不直接从项目文件夹运行 docker 生成。

此操作会创建一个名为 cesardl/netcore-webapi-microservice-docker:first 的 Docker 映像。 此处的 :first 是表示特定版本的标记。 为组合 Docker 应用程序创建自定义映像时，可为每个映像重复执行此步骤。

应用程序由多个容器组成时（即多容器应用程序），还可使用 docker-compose up --build 命令，借助相关 docker-compose.yml 文件中公开的元数据，只需一个命令即可生成所有相关映像。

使用 docker images 命令可查找本地存储库中的现有映像，如图 5-6 所示。

![](./media/image9.png)

**如 5-6**。 使用 docker images 命令查看现有映像

### <a name="creating-docker-images-with-visual-studio"></a>使用 Visual Studio 创建 Docker 映像

使用 Visual Studio 创建带 Docker 支持的项目时，不会显式创建映像。 开发人员按下 F5 并运行已 Docker 化的应用程序或服务时，Visual Studio 就会创建映像。 Visual Studio 会自动执行此操作，不会出现明显的过程，但开发人员需要了解其原理。

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>步骤 4。 生成多容器 Docker 应用程序时，在 docker-compose.yml 中定义服务

借助 [docker-compose.yml](https://docs.docker.com/compose/compose-file/) 文件，开发人员可定义一组相关服务，通过部署命令将其部署为组合应用程序。

若要使用 docker-compose.yml 文件，则需在主解决方案文件夹或根解决方案文件夹中创建该文件，其内容与以下示例中的内容类似：

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

请注意，这是一个简化合并版的 docker-compose.yml 文件。 其中包含始终适用的每个容器的静态配置数据（如自定义映像的名称），以及视部署环境而定的配置信息（如连接字符串）。 后面的章节将介绍如何将 docker-compose.yml 配置拆分为多个 docker-compose 文件，并根据环境和执行类型（调试或发布）覆盖值。

docker-compose.yml 示例文件中定义了五项服务：webmvc 服务（一个 Web 应用程序）、两个微服务（catalog.api 和 ordering.api）、一个数据源容器以及一个作为容器运行的基于 SQL Server for Linux 的 sql.data。 每项服务都部署为一个容器，因此每项服务都需要一个 Docker 映像。

docker-compose.yml 文件不仅指定正在使用的容器，还指定如何单独配置各容器。 例如，.yml 文件中的 webmvc 容器定义：

-   使用预生成的 eshop/web:latest 映像。 但也可以借助基于 docker-compose 文件中 build: 部分的其他配置，在执行 docker-compose 的过程中配置要生成的映像。

-   初始化两个环境变量（CatalogUrl 和 OrderingUrl）。

-   将容器上的公开端口 80 转接到主机上的外部端口 80。

-   通过 depends\_on 设置将 Web 应用链接到目录和排序服务。 此操作会让该服务处于等待状态，直到启用这些服务。

稍后介绍如何实现微服务和多容器应用时，我们会再次回顾 docker-compose.yml 文件。

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>在 Visual Studio 2017 中使用 docker-compose.yml

如图 5-7 所示，向 Visual Studio 解决方案中的服务项目添加对 Docker 解决方案的支持时，Visual Studio 会向项目添加 Dockerfile，且会通过 docker-compose.yml 文件在解决方案中添加一个服务部分（项目）。 通过这种方式可以轻松开始编写多容器解决方案。 随后可打开 docker-compose.yml 文件并对其进行更新，增加新的功能。

![](./media/image6.png)

**图 5-7**。 右键单击 ASP.NET Core 项目，在 Visual Studio 2017 中添加对 Docker 的支持

在 Visual Studio 中添加对 Docker 的支持时，不仅会向项目添加 Dockerfile，还会向在解决方案级设置的多个全局 docker-compose.yml 文件添加配置信息。

在 Visual Studio 中添加对 Docker 的支持后，解决方案资源管理器中会出现一个新节点（位于 docker-compose.dcproj 项目文件中），其中包含添加的 docker-compose.yml 文件，如图 5-8 所示。

![](./media/image11.PNG)

**图 5-8**。 在 Visual Studio 2017 解决方案资源管理器中添加的 docker-compose 树节点

可使用 docker-compose up 命令，通过单个 docker-compose.yml 文件部署多容器应用程序。 但 Visual Studio 按组添加，因此开发人员可根据环境（开发与生产）和执行类型（发布与调试）来覆盖值。 稍后将介绍此功能。

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>步骤 5。 生成并运行 Docker 应用程序

如果应用程序只有一个容器，则可通过将其部署到 Docker 主机（虚拟机或物理服务器）来运行该程序。 但如果应用程序包含多项服务，则可使用单个 CLI 命令 (docker-compose up) 或使用 Visual Studio（会在其中使用该命令）将其部署为组合应用程序。 接下来介绍这两种不同的选项。

### <a name="option-a-running-a-single-container-with-docker-cli"></a>选项 A：使用 Docker CLI 运行单容器

可使用 docker run 命令运行 Docker 容器，如图 5-9 所示：

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**图 5-9**。 使用 docker run 命令运行 Docker 容器

此时，该命令将容器的内部端口 5000 绑定到主机的端口 80。 这意味着主机在侦听端口 80，并将其转接到容器上的端口 5000。

### <a name="option-b-running-a-multi-container-application"></a>选项 B：运行多容器应用程序

在大多数企业方案中，Docker 应用程序由多项服务组成，这意味着需要运行多容器应用程序，如图 5-10 所示。

![](./media/image14.png)

**图 5-10**。 部署了 Docker 容器的 VM

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>使用 Docker CLI 运行多容器应用程序

若要使用 Docker CLI 运行多容器应用程序，可运行 docker-compose up 命令。 此命令使用解决方案级别的 docker-compose.yml 文件来部署多容器应用程序。 图 5-11 显示了从主项目目录（包含 docker-compose.yml 文件）运行命令的结果。

![](./media/image15.png)

**图 5-11**。 运行 docker-compose up 命令时的示例结果

运行 docker-compose up 命令后，应用程序及其相关容器将部署到 Docker 主机中，如图 5-10 中的 VM 所示。

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>使用 Visual Studio 运行和调试多容器应用程序 

使用 Visual Studio 2017 运行多容器应用程序十分简单。 使用 Visual Studio 不仅可以运行多容器应用程序，还可通过设置常规断点直接在 Visual Studio 中调试程序的所有容器。

如前所述，每次向解决方案中的项目添加对 Docker 的支持时，都会在全局（解决方案级别）docker-compose.yml 文件中配置该项目，因此开发人员可以同时运行或调试整个解决方案。 Visual Studio 将为每个启用了 Docker 解决方案支持的项目启动一个容器，并代为执行所有内部步骤（发布 dotnet、生成 Docker 等）。

此处的重点是，在 Visual Studio 2017 中，按下 F5 键可执行另一项 Docker 命令，如图 5-12 所示。 此选项允许开发人员在解决方案级别运行 docker-compose.yml 文件中定义的所有容器，从而运行或调试多容器应用程序。 可调试多容器解决方案就意味着，开发人员可设置多个断点，每个端点都位于不同的项目（容器）中，这样从 Visual Studio 进行调试时，会在不同项目中定义的断点处停止，并在不同容器上运行。

![](./media/image16.png)

**图 5-12**。 在 Visual Studio 2017 中运行多容器应用

### <a name="additional-resources"></a>其他资源

-   **将 ASP.NET 容器部署到远程 Docker 主机**
    [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>有关使用业务流程协调程序进行测试和部署的注意事项

使用 docker-compose up 和 docker run 命令（或在 Visual Studio 中运行和调试容器）足以在开发环境中测试容器。 但如果对象是 Docker 群集和业务流程协调程序（如 Docker Swarm、Mesosphere DC/OS 或 Kubernetes），则不应使用此方法。 如果使用 [Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（自 1.12 版起可用于 Windows 和 Mac 适用的 Docker CE）等集群，则需使用 [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) 等附加命令部署和测试单个服务。 如果要部署由多个容器组成的应用程序，请使用 [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) 和 [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) 将组合应用程序部署为堆栈。 有关详细信息，请参阅 Docker 文档中的博客文章 [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/)（实验得出的分布式应用程序捆绑报简介）。 请访问 Docker 站点。

对于 [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) 和 [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/)，也可使用不同的部署命令和脚本。

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>步骤 6。 使用本地 Docker 主机测试 Docker 应用程序

这一步骤会因应用程序的用途而有所不同。 对于部署为单个容器或服务的简单 .NET Core Web 应用程序而言，在 Docker 主机上打开浏览器并导航到该站点即可访问该服务，如图 5-13 所示。 （如果 Dockerfile 中的配置将容器映射到除主机上的 80 端口以外的任何端口，请在 URL 中包含该主机端口。）

![](./media/image18.png)

**图 5-13**。 使用 localhost 在本地测试 Docker 应用程序的示例

如果 localhost 未指向 Docker 主机 IP（默认情况下，使用 Docker CE 时应指向主机 IP），若要导航到服务，请使用计算机网卡的 IP 地址。

请注意，在此处讨论的特定容器示例中，浏览器中的此 URL 使用的是端口 80。 但该请求会在内部被重定向到端口 5000，因为 docker run 命令之前进行了此部署，如上一步中所述。

还可从终端使用 curl 测试应用程序，如图 5-14 所示。 对于 Windows 上安装的 Docker，除计算机的实际 IP 地址以外，默认的 Docker 主机 IP 始终为 10.0.75.1。

![](./media/image19.png)

**图 5-14**。 使用 curl 在本地测试 Docker 应用程序的示例

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>使用 Visual Studio 2017 测试和调试容器

使用 Visual Studio 2017 运行和调试容器时，调试 .NET 应用程序的方式与运行不带容器的应用程序的方式类似。

### <a name="testing-and-debugging-without-visual-studio"></a>不使用 Visual Studio 进行测试和调试

如果使用编辑器/CLI 方法开发应用，调试容器会更加困难，需通过生成跟踪来进行调试。

### <a name="additional-resources"></a>其他资源

-   **在本地 Docker 容器中调试应用**
    [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker。Build, Debug, Deploy ASP.NET Core Apps with Docker**（使用 Docker 生成、调试、部署 ASP.NET Core 应用）。 视频。
    [https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>使用 Visual Studio 可简化开发容器的工作流

实际上，使用 Visual Studio 进行开发的工作流比使用编辑器/CLI 方法的工作流简单得多。 Visual Studio 隐藏或简化了 Docker 需要执行的与 Dockerfile 和 docker-compose.yml 文件相关的大部分步骤，如图 5-15 所示。

![](./media/image20.png)

**图 5-15**。 使用 Visual Studio 可简化开发工作流

此外，只需执行一次第 2 步（向项目添加对 Docker 的支持）。 因此，该工作流与使用 .NET 进行任何其他开发时的普通开发任务的工作流类似。 开发人员需要了解其背后的工作原理（映像生成过程，使用的基础映像，容器的部署等），有时还需要编辑 Dockerfile 或 docker-compose.yml 文件以自定义行为。 但 Visual Studio 大大简化了大部分工作，提高了工作效率。

### <a name="additional-resources"></a>其他资源

-   **Steve Lasker. .NET Docker Development with Visual Studio 2017**（使用 Visual Studio 2017 进行 .NET Docker 开发）
    [https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey T. Fritz。使用 Visual Studio 的新 Docker 工具将 .NET Core 应用放入容器中**
    [https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>在 DockerFile 中使用 PowerShell 命令来设置 Windows 容器 

[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)允许开发人员将现有 Windows 应用程序转换为 Docker 映像，并使用与 Docker 生态系统其余部分相同的工具进行部署。 若要使用 Windows 容器，请在 Dockerfile 中运行 PowerShell 命令，如以下示例所示：

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

本示例中使用的是 Windows Server Core 基础映像（FROM 设置），并使用 PowerShell 命令（RUN 设置）来安装 IIS。 同样，也可使用 PowerShell 命令来设置其他组件，如 ASP.NET 4.x、.NET 4.6 或任何其他 Windows 软件。 例如，Dockerfile 中的以下命令可设置 ASP.NET 4.5：

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>其他资源

-   **aspnet-docker/Dockerfile。** Example Powershell commands to run from dockerfiles to include Windows features（在 dockerfiles 中运行以包含 Windows 功能的 Powershell 命令示例）。
    [https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[上一篇] (index.md) [下一篇] (../net-core-single-containers-linux-windows-server-hosts/index.md)
