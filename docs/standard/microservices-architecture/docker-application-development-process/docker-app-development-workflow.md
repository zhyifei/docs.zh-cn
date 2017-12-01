---
title: "Docker 应用的开发工作流"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |Docker 应用的开发工作流"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a>Docker 应用的开发工作流

应用程序开发生命周期开始每个开发人员的计算机，其中开发人员代码使用其首选的语言的应用程序和本地测试它。 无论哪个语言、 框架和平台选择开发人员，借助此工作流，开发人员始终开发和测试 Docker 容器，但是本地执行此操作。

每个容器 （Docker 映像的实例） 包括以下组件：

-   操作系统选择 （例如，一种 Linux 分发，Windows Nano Server 或 Windows Server Core）。

-   由开发人员 （应用程序二进制文件等） 添加的文件。

-   （环境设置及依赖关系） 的配置信息。

## <a name="workflow-for-developing-docker-container-based-applications"></a>有关在开发 Docker 容器基于应用程序的工作流

本部分介绍*内部循环*Docker 容器基于应用程序的开发工作流。 内部循环工作流意味着它不会占用考虑更广泛的 DevOps 工作流，并只重点介绍在开发人员计算机上完成开发工作。 设置环境的初始步骤不包括，，因为这些中进行一次。

应用程序组成你自己的服务和其他库 （依赖项）。 以下是你通常执行时生成 Docker 应用程序，如图 5-1 中所示的基本步骤。

![](./media/image1.png)

**图 5-1。** 开发 Docker 容器化应用程序的分步工作流

本指南中详细介绍了此整个过程和每个主要步骤通过将重点放在 Visual Studio 环境上所述。

当你使用的编辑器/CLI 开发方法 （例如，Visual Studio 代码以及在 macOS 上的 Docker CLI 或 Windows） 时，你需要知道每个步骤中，通常比使用 Visual Studio 的更详细地。 有关使用 CLI 环境中的更多详细信息，请参阅电子书[与 Microsoft 平台和工具的容器的 Docker 应用程序生命周期](http://aka.ms/dockerlifecycleebook/)。

当你使用 Visual Studio 2015 或 Visual Studio 2017 时，许多这些步骤会替你处理，这将显著提高工作效率。 当你使用 Visual Studio 2017 并且面向多容器应用程序，也是如此。 例如，只在一个鼠标单击 Visual Studio Dockerfile 并将其 docker-compose.yml 将文件添加到您的项目与你的应用程序的配置。 Visual Studio 中运行应用程序时，它能够构建 Docker 映像和直接在 Docker; 运行多容器应用程序它甚至可以同时调试多个容器。 这些功能将大大提高开发速度。

但是，只是因为 Visual Studio 使这些步骤自动并不意味着不需要知道哪些是使用 Docker 后台。 因此，在下面的指引，我们详细介绍每个步骤。

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>步骤 1。 开始编码并创建初始应用程序或服务基线

开发 Docker 应用程序是开发应用程序，而 Docker 不工作方式相似。 区别是，开发时对 Docker，你部署和测试您的应用程序或服务在本地环境中的 Docker 容器内运行。 容器可以是 Linux 容器或 Windows 容器。

### <a name="set-up-your-local-environment-with-visual-studio"></a>设置本地环境使用 Visual Studio

若要开始，请确保你具有[Docker 社区版 (CE)](https://www.docker.com/community-edition)适用于 Windows 安装，如下面的说明中所述：

[要开始使用 CE 用于 Windows 的 Docker](https://docs.docker.com/docker-for-windows/)

此外，你将需要安装的 Visual Studio 2017。 这是首选通过 Visual Studio 2015 使用 Visual Studio Tools for Docker 外接程序，因为 Visual Studio 2017 具有更高级的支持 Docker，如对调试容器的支持。 Visual Studio 2017 包括 Docker 的工具，如果你选择**.NET 核心和 Docker**在安装期间，在图 5-2 中所示的工作负荷。

![](./media/image3.png)

**图 5-2**。 选择**.NET 核心和 Docker**在 Visual Studio 2017 安装过程的工作负荷

即使之前，应用程序中启用 Docker 和部署和测试在 Docker 中启动编码 （通常在.NET 核心如果你打算使用容器） 中的纯.NET 中的应用程序。 但是，建议你开始使用 Docker 上尽可能快，因为这将是对实际环境，并且可以尽可能快地发现任何问题。 这因为 Visual Studio 使因此用户可轻松地使用 Docker，它几乎外观透明鼓励-调试从 Visual Studio 的多容器应用程序时的最佳示例。

### <a name="additional-resources"></a>其他资源

-   **要开始使用 CE 用于 Windows 的 Docker**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio 2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>步骤 2。 创建与现有的.NET 基映像相关 Dockerfile

你需要为你想要生成; 每个自定义图像的 Dockerfile你还需要每个容器的 Dockerfile，若要部署，是否自动从 Visual Studio 或使用 Docker CLI 手动部署 (运行的 docker 和 docker-撰写命令)。 如果你的应用程序包含单个自定义服务，则需要单个 Dockerfile。 如果你的应用程序包含多个服务 （如所示的微服务体系结构），你将需要一个 Dockerfile，为每个服务。

Dockerfile 放置在应用程序或服务的根文件夹中。 它包含告诉 Docker 如何设置和容器中运行应用程序或服务的命令。 你可以手动在代码中创建 Dockerfile 和将其添加到你的项目，.NET 依赖项。

使用 Visual Studio 和 Docker 其工具，此任务需要仅单击几下鼠标。 当你在 Visual Studio 2017 年 1 中创建新项目时，可选择名为**启用容器 (Docker) 支持**，如图 5-3 中所示。

![](./media/image5.png)

**图 5-3**。 在 Visual Studio 2017 年 1 中创建新项目时启用 Docker 的支持

此外可以通过右键单击你在 Visual Studio 中的项目文件并选择选项来启用对新的或现有项目的 Docker 支持**添加 Docker 项目支持**，如图 5-4 中所示。

![](./media/image6.png)

**图 5-4**。 在现有 Visual Studio 2017 项目中的启用 Docker 支持

此操作 （如 ASP.NET Web 应用程序或 Web API 服务） 项目将添加到具有所需的配置项目的 Dockerfile。 它还添加了整个解决方案的 docker-compose.yml 文件。 在以下部分中，我们将介绍将进入每个文件的信息。 Visual Studio 可为你完成此工作，但它可用于了解哪些内容放到 Dockerfile。

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>选项 a： 创建项目使用现有官方.NET Docker 映像

通常在你可以从在正式存储库的基本映像之上容器生成自定义映像[Docker Hub](https://hub.docker.com/)注册表。 这确切地说是时会发生什么情况下启用 Visual Studio 中的 Docker 支持。 Dockerfile 将使用现有 aspnetcore 映像。

前面我们介绍了哪些 Docker 映像和存储库可以使用，具体取决于框架和你已选择的操作系统。 例如，如果你想要使用 ASP.NET Core （Linux 或 Windows），要使用的图像是 microsoft / aspnetcore:2.0。 因此，你只需指定将用于你的容器哪些基本 Docker 映像。 执行此操作通过从 microsoft 添加 / aspnetcore:2.0 到 Dockerfile。 这将由 Visual Studio 中，自动执行，但如果你是更新的版本，则更新此值。

从 Docker Hub 官方.NET 映像存储库使用的版本号，可确保相同的语言功能是可用 （包括开发、 测试和生产） 的所有计算机上。

下面的示例显示了一个示例 Dockerfile ASP.NET Core 容器。

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

在这种情况下，容器基于版本 2.0 的官方 ASP.NET 核心 Docker 映像 （适用于 Linux 和 Windows 多体系结构）。 这是设置`FROM microsoft/aspnetcore:2.0`。 (有关此基本映像的详细信息，请参阅[ASP.NET Core Docker 映像](https://hub.docker.com/r/microsoft/aspnetcore/)页和[.NET Core Docker 映像](https://hub.docker.com/r/microsoft/dotnet/)页。)Dockerfile，还需要指示 Docker 在你将在运行时 （在此情况下，端口 80，如使用公开设置配置） 使用的 TCP 端口上侦听。

Dockerfile，具体取决于的语言和框架正在使用中，可以指定其他配置设置。 例如，使用的入口点行\["dotnet"，"MySingleContainerWebApp.dll"\]告知 Docker 运行.NET 核心应用程序。 如果你使用 SDK 和.NET 核心 CLI (dotnet CLI) 生成并运行.NET 应用程序，此设置会有所不同。 底部行是入口点行和其他设置将无法为应用程序选择的语言和平台而异。

### <a name="additional-resources"></a>其他资源

-   **.NET 核心应用程序的构建 Docker 映像**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)

-   **生成你自己的映像**。 在正式的 Docker 文档。
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>使用多 arch 映像存储库

单个存储库可以包含平台的不同版本，如 Linux 映像和 Windows 映像。 此功能，如 Microsoft （基本映像创建者） 供应商创建的单个存储库以涵盖多个平台 （这是 Linux 和 Windows）。 例如， [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) Docker Hub 注册表中的可用存储库通过使用相同的存储库名称提供了适用于 Linux 和 Windows Nano Server 的支持。

如果指定的标记，面向的平台的显式诸如在以下情况：

-   **microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

但是，并且这是新自后中旬 2017，如果你指定的相同的映像名称，即使使用相同的标记，新的多 arch 映像 （如支持多体系结构 aspnetcore 映像） 将使用的 Linux 或 Windows 的版本，具体取决于要部署的 Docker 主机操作系统如下面的示例中所示：

-   **microsoft / aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

这样，当你从 Windows 主机请求映像时，它将请求 Windows 变体，并且从 Linux 主机提取相同的映像名称将请求 Linux 变体。

### <a name="option-b-creating-your-base-image-from-scratch"></a>选项 b： 创建您从零开始的基础映像

你可以从头开始创建你自己 Docker 的基本映像。 这种情况下不建议的人员开始使用 Docker，但如果你想要设置自己的基本映像的特定位，则可以这样。

### <a name="additional-resources"></a>其他资源

-   **多 arch.NET Core 映像**。
https://github.com/dotnet/announcements/issues/14 
-   **创建基本映像**。 Docker 的正式文档。
    [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>步骤 3。 创建自定义的 Docker 映像和在它们中嵌入应用程序或服务

对于应用程序中每个服务，你需要创建相关的映像。 如果你的应用程序有一个服务或 web 应用程序组成，只需单个映像。

请注意，Docker 映像生成自动为你在 Visual Studio 中。 以下步骤只需要编辑器/CLI 工作流和为清楚起见相关下会发生什么情况的说明。

作为开发人员，需要开发和测试本地直到你推送已完成功能，或将更改为源代码管理系统 （例如，若要 GitHub)。 这意味着你需要创建的 Docker 映像和部署到本地的 Docker 主机 （Windows 或 Linux VM） 的容器和运行、 测试和调试针对这些本地的容器。

若要在本地环境中创建自定义映像，通过 Docker CLI 和 Dockerfile，可以使用 docker 生成命令，如图 5-5 中。

![](./media/image8.png)

**图 5-5**。 创建自定义的 Docker 映像

（可选） 而不是直接从项目文件夹运行 docker 生成，你可以首先生成具有所需的.NET 库的可部署文件夹并通过运行 dotnet 的二进制文件发布，然后使用 docker 生成命令。

这将创建名称 cesardl/netcore webapi-微服务构成的 Docker 映像-docker： 第一个。 在这种情况下，： 首先是表示特定版本的标记。 你需要创建 Docker 应用程序由每个自定义映像，可以重复此步骤。

当应用程序由多个容器 （即，它是一个多容器应用程序），你还可以使用 docker compose 向上-生成命令，以使用在相关的中公开的元数据生成使用单个命令的所有相关的映像docker-compose.yml 文件。

你可以找到现有的映像在本地存储库中使用 docker 映像命令，在图 5-6 中所示。

![](./media/image9.png)

**图 5-6。** 查看现有的映像使用 docker 映像命令

### <a name="creating-docker-images-with-visual-studio"></a>使用 Visual Studio 中创建 Docker 映像

当你使用 Visual Studio 与 Docker 支持创建项目时，你未显式创建映像。 相反，创建映像为你在按 F5 并运行 dockerized 应用程序或服务。 此步骤是自动在 Visual Studio 中，和你看不到这种情况，但很重要，你知道这一点后台。

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>步骤 4。 构建多容器 Docker 应用程序时在 docker-compose.yml 中定义你的服务

[Docker-compose.yml](https://docs.docker.com/compose/compose-file/)文件，您可以定义一组相关的服务，若要部署为一个由应用程序使用部署命令。

若要使用 docker-compose.yml 文件，需要创建你 main 中的文件或根解决方案文件夹中，使用类似于下面的示例中的内容：

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

请注意，此 docker-compose.yml 文件简化并已合并的版本。 它包含每个容器 （如自定义映像的名称中），它始终适用，加上可能取决于部署环境，如连接字符串的配置信息的静态配置数据。 在后面的部分，你将了解如何可以拆分成多个 docker-compose.yml 配置 docker 编写的文件和重写值根据环境和执行类型 （调试或发布）。

Docker-compose.yml 文件示例定义了五个服务： webmvc 服务 （web 应用程序）、 两个微服务 （catalog.api 和 ordering.api） 和一个数据源容器，sql.data，基于适用于 Linux 容器作为运行 SQL Server。 每个服务部署为一个容器，因此 Docker 映像需要为每个。

Docker-compose.yml 文件指定不仅正在使用哪些容器，但它们单独配置的方式。 例如，webmvc 容器中的定义.yml 文件：

-   使用预建电子商店 / web： 最新映像。 但是，你也可以配置要作为的一部分生成的映像 docker 撰写基于生成的执行额外的配置： docker-compose 文件中的部分。

-   初始化两个环境变量 （CatalogUrl 和 OrderingUrl）。

-   将转发公开的端口 80 上容器主机上的外部端口 80。

-   链接到该目录并进行排序来与服务的 web 应用取决于\_上设置。 这会导致服务等待，直到启动这些服务。

当我们涵盖如何实现微服务和多容器应用程序时，我们将重温后面的部分中的 docker-compose.yml 文件。

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>使用在 Visual Studio 2017 docker-compose.yml

图 5-7 中所示 Docker 解决方案支持添加到在 Visual Studio 解决方案中，服务项目，Visual Studio 将 Dockerfile 添加到你的项目，并 docker-compose.yml 文件解决方案中添加服务部分 （项目）。 它是开始编写你的多个容器解决方案的简单办法。 然后，你可以打开 docker-compose.yml 文件，并更新它们具有附加功能。

![](./media/image6.png)

**图 5-7**。 通过右击 ASP.NET Core 项目在 Visual Studio 2017 中添加 Docker 支持

在 Visual Studio 中添加 Docker 支持不仅能将 Dockerfile 添加到你的项目，还将配置信息添加到在解决方案级别设置的多个全局 docker-compose.yml 文件。

将 Docker 支持添加到你在 Visual Studio 中的解决方案后，你还将看到包含添加的 docker-compose.yml 文件中，在图 5-8 中所示的解决方案资源管理器中的新节点 （在 docker compose.dcproj 项目文件中）。

![](./media/image11.PNG)

**图 5-8**。 **Docker compose**添加在 Visual Studio 2017 解决方案资源管理器的树节点

可以使用单个 docker-compose.yml 文件中部署多容器应用程序通过 docker compose 命令。 但是，Visual Studio 将一组添加它们以便您可以覆盖根据环境 （而不是生产开发） 和执行的值类型 （而不是调试版本）。 此功能将在后面的部分中所述。

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>步骤 5。 生成并运行你的 Docker 应用程序

如果你的应用程序中只有单个容器，你可以通过将其部署到你的 Docker 主机 （VM 或物理服务器） 来运行它。 但是，如果你的应用程序包含多个服务，你可以将其部署为一个由应用程序，使用单个 CLI 命令 （docker-撰写向上），或使用 Visual Studio，它将使用事实上该命令。 我们来看的不同选项。

### <a name="option-a-running-a-single-container-with-docker-cli"></a>选项 a： 使用 Docker CLI 运行单容器

你可以运行使用 docker 运行命令，如图 5-9 中的 Docker 容器：

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**图 5-9**。 运行使用 docker run 命令的 Docker 容器

在这种情况下，该命令将容器的内部端口 5000 绑定到主机的端口 80。 这意味着在端口 80 上侦听并转发到端口 5000 上容器主机。

### <a name="option-b-running-a-multi-container-application"></a>选项 b： 运行多容器应用程序

在大多数的企业方案中，Docker 应用程序将由构成的多个服务，这意味着你需要运行多容器应用程序，如图 5-10 中所示。

![](./media/image14.png)

**图 5-10**。 与部署的 Docker 容器的 VM

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>使用 Docker CLI 运行多容器应用程序

若要使用 Docker CLI 运行多容器应用程序，你可以运行 docker-撰写命令。 在解决方案级别部署多容器应用程序具有此命令使用 docker-compose.yml 文件。 图 5-11 从主项目目录，其中包含 docker-compose.yml 文件运行命令时显示的结果。

![](./media/image15.png)

**图 5-11**。 运行时结果示例 docker compose 命令

后 docker-撰写向上命令运行，应用程序和其相关的容器部署到你的 Docker 主机，如图 5-10 中的 VM 表示中所示。

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>运行和调试使用 Visual Studio 的多容器应用程序 

运行使用 Visual Studio 2017 的多容器应用程序无法获取更简单。 您可以不仅运行多容器应用程序，但你能够通过设置正则断点调试其直接从 Visual Studio 的所有容器。

如前所述，每次你 Docker 解决方案将支持添加到解决方案中的项目，该项目配置在全局 （解决方案级） docker-compose.yml 文件中，这样就可以运行或在一次调试整个解决方案中。 Visual Studio 将启动一个容器的 Docker 解决方案启用了支持，每个项目，并为你执行内部的所有步骤 （dotnet 发布，docker 生成，等等。）。

重要的一点是，如所示图 5-12 中，在 Visual Studio 2017 还有一个额外**Docker** F5 键操作的命令。 此选项允许你运行或调试多容器应用程序正在运行的解决方法级别的 docker-compose.yml 文件中定义的所有容器。 调试多个容器解决方案的能力意味着你可以在不同的项目 （容器），设置多个断点，每个断点，并从 Visual Studio 进行调试时你可以停止在断点在不同项目中定义和上运行不同的容器。

![](./media/image16.png)

**图 5-12**。 在 Visual Studio 2017 中运行多容器应用程序

### <a name="additional-resources"></a>其他资源

-   **将 ASP.NET 容器部署到远程 Docker 主机**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>有关测试和使用 orchestrators 部署的注意事项

向上 docker compose 和 docker 运行命令 （或运行调试 Visual Studio 中的容器），而对于在你的开发环境中测试容器。 但如果你面向的 Docker 群集且 orchestrators 喜欢 Docker Swarm、 Mesosphere DC/OS 或 Kubernetes，则不应使用此方法。 如果你使用群集例如[Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（适用于 Docker CE for Windows 和 Mac 自版本 1.12），你需要部署和测试与其他命令，如[docker 服务创建](https://docs.docker.com/engine/reference/commandline/service_create/)为单个服务。 如果你要部署的多个容器构成应用程序，则使用[docker compose 捆绑](https://docs.docker.com/compose/reference/bundle/)和[docker 部署 myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/)部署由应用程序作为*堆栈*. 有关详细信息，请参阅博客文章[简介实验的分布式应用程序捆绑包](https://blog.docker.com/2016/06/docker-app-bundle/)Docker 文档中。 上的 Docker 站点。

有关[DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/)和[Kubernetes](http://kubernetes.io/docs/user-guide/deployments/)你会使用不同的部署命令和脚本以及。

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>步骤 6。 测试 Docker 应用程序使用本地 Docker 主机

此步骤根据你的应用程序正在执行什么操作会有所不同。 在部署为单个容器或服务的简单.NET 核心 Web 应用，你可以通过打开 Docker 主机上的浏览器并导航到该站点，在图 5-13 中所示来访问服务。 （如果 Dockerfile 中的配置将容器映射到是 80 之外的任何主机上的端口，包括主机后在 URL 中。）

![](./media/image18.png)

**图 5-13**。 测试本地使用 localhost Docker 应用程序的示例

如果 localhost 不指向 Docker 主机 IP （默认情况下，当使用 Docker CE 时，它应），若要导航到你的服务时，使用计算机的网络卡的 IP 地址。

请注意此 URL 在浏览器中的，对于所讨论的特定容器示例使用端口 80。 但是，内部请求会重定向到端口 5000，因为这是它的部署方式与 docker 运行命令上, 一步中所述。

图 5-14 中所示，你还可以测试使用从终端，curl 的应用程序。 在 Windows 上的 Docker 安装，默认 Docker 主机 IP 始终是 10.0.75.1 除了您的计算机的实际 IP 地址。

![](./media/image19.png)

**图 5-14**。 测试本地使用 curl Docker 应用程序的示例

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>测试和调试使用 Visual Studio 2017 容器

当运行和调试使用 Visual Studio 2017 容器，你可以在基本相同的方法中调试.NET 应用程序，就像没有容器的情况下运行时。

### <a name="testing-and-debugging-without-visual-studio"></a>测试和调试而无需 Visual Studio

如果你正在开发使用编辑器/CLI 方法，调试容器的难度，并且你将想要调试生成跟踪。

### <a name="additional-resources"></a>其他资源

-   **本地 Docker 容器中调试应用程序**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker。生成、 调试、 部署使用 Docker 的 ASP.NET Core 应用。** 视频。
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>在开发使用 Visual Studio 的容器时的简化工作流

实际上，工作流时使用 Visual Studio 会比在使用的编辑器/CLI 方法大量更简单。 与 Dockerfile 相关的大多数步骤所需的 Docker，隐藏或图 5-15 中所示，由 Visual Studio 中，简化 docker-compose.yml 文件。

![](./media/image20.png)

**图 5-15**。 简化工作流时使用 Visual Studio 进行开发

此外，你需要执行步骤 2 （向你的项目添加 Docker 支持） 只需一次。 因此，工作流时使用的任何其他开发.NET 是类似于常用的开发任务。 你需要知道发生了什么情况 （映像生成过程、 哪些正在使用的基础映像、 部署的容器，等等） 在后台，有时你还需要编辑 Dockerfile 或 docker-compose.yml 文件，可以自定义行为。 但是，通过使用 Visual Studio 中，使大量提高工作效率极大地简化的大部分工作。

### <a name="additional-resources"></a>其他资源

-   **Steve Lasker。使用 Visual Studio 2017 的.NET docker 开发**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey t。 Fritz。For Visual Studio.NET 核心应用程序放入新的 Docker 工具与容器**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>使用在 Dockerfile 中的 PowerShell 命令来设置 Windows 容器 

[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)允许你将现有的 Windows 应用程序转换为 Docker 映像并将其部署与 Docker 生态系统的其余部分所在的相同工具。 若要使用 Windows 容器，你运行 PowerShell 命令在 Dockerfile，如下面的示例中所示：

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

在这种情况下，我们已使用 Windows Server Core 基本映像 （FROM 设置），并使用 PowerShell 命令 （运行设置） 安装 IIS。 以类似的方式，还可以使用 PowerShell 命令来设置其他组件，如 ASP.NET 4.x、.NET 4.6 或任何其他 Windows 软件。 例如，Dockerfile 中的以下命令将设置 ASP.NET 4.5:

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>其他资源

-   **aspnet-docker/Dockerfile。** 示例 Powershell 命令，以从 dockerfile 以包括 Windows 功能运行。
    [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[以前](index.md) [下一步] (.../ net-core-single-containers-linux-windows-server-hosts/index.md）
