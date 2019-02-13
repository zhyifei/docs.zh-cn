---
title: Docker 应用的内部循环开发工作流
description: 了解开发 Docker 应用程序的"内部循环"工作流。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 03eb4662e55551678105fa9ef25b42cc05c132a5
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219083"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Docker 应用的内部循环开发工作流

触发跨越整个 DevOps 的外部循环工作流之前循环，开始整个过程的每个开发人员的计算机上，应用本身进行编码、 使用其首选的语言或平台，以及本地测试 (图 4-14)。 但在所有情况下，你必须非常重要的一点共同点，无论选择何种语言、 框架或平台。 在此特定的工作流，始终是开发和测试 Docker 容器，但却在本地。

![](./media/image18.png)

图 4-14:内部循环开发上下文

容器或 Docker 映像的实例将包含这些组件：

-   选择 （例如，Linux 分发版或 Windows） 的操作系统

-   由开发人员 （例如，应用程序二进制文件） 添加的文件

-   配置 （例如，环境设置和依赖项）

-   哪些过程操作即可运行 Docker 的说明

您可以将设置为 （下一节中所述） 的过程中使用 Docker 的内部循环开发工作流。 考虑设置环境的初始步骤不包括在内，因为您需要为此，只需一次。

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>构建单个应用程序中使用 Visual Studio Code 和 Docker CLI 的 Docker 容器

应用是从你自己的服务和附加库 （依赖项） 组成。

图 4-15 显示了通常需要构建 Docker 应用程序后, 跟每个步骤的详细说明时要执行的基本步骤。

![](./media/image19.png)

图 4 月 15 日：使用 Docker CLI 适用于容器化 Docker 应用程序生命周期的高级工作流

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>步骤 1：开始在 Visual Studio Code 中编写代码并创建初始应用/服务基线

开发应用程序的方法是执行不带 Docker 的方式非常类似。 不同之处是，在开发时，在部署和测试应用程序或服务 （如 Windows 或 Linux VM） 在本地环境中放置的 Docker 容器中运行。

**设置本地环境**

使用适用于 Mac 和 Windows 的 Docker 的最新版本，比以往要开发 Docker 应用程序更容易和安装程序非常简单。

**详细信息** 有关 Docker 的 Windows 设置的说明，请转到[ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/)。

有关设置 Docker for Mac 的说明，请转到<https://docs.docker.com/docker-for-mac/>。

此外，还需要代码编辑器，以便您可以实际开发正在使用 Docker CLI 的应用程序。

Microsoft 提供了 Visual Studio Code 中，这是一个轻量级代码编辑器，支持在 Mac、 Windows、 和 Linux，并提供与 IntelliSense[支持多种语言](https://code.visualstudio.com/docs/languages/overview)(JavaScript、.NET、 Go、 Java、 Ruby、 Python 和大部分现代语言）、[调试](https://code.visualstudio.com/Docs/editor/debugging)，[与 Git 集成](https://code.visualstudio.com/Docs/editor/versioncontrol)并[扩展插件支持](https://code.visualstudio.com/docs/extensions/overview)。 此编辑器是非常适合用于 Mac 和 Linux 的开发人员。 在 Windows 中，您还可以使用完整的 Visual Studio 应用程序。

**详细信息** 安装 Visual Studio 为 Windows、 Mac 或 Linux 的说明，请转到<https://code.visualstudio.com/docs/setup/setup-overview/>。

可以使用 Docker CLI 和写入你的代码使用任何代码编辑器中，但如果使用 Visual Studio Code，可以轻松编写 Dockerfile 和 docker-compose.yml 文件在工作区中。 此外，可以从 IDE 提示可以运行使用下方的 Docker CLI 的详细的操作的脚本运行 Visual Studio Code 任务。

Visual Studio Code 提供的扩展，但需要进行安装。 若要执行此操作，按 Ctrl + Shift + P，键入**ext 安装**，然后运行扩展：安装扩展命令以打开 Marketplace 扩展列表。 接下来，键入**docker**以筛选结果，然后选择 Dockerfile 和 Docker Compose 文件 (yml) 支持扩展，如下图中图 4-16 所示。

![](./media/image20.png)

图 4-16:在 Visual Studio Code 中安装 Docker 扩展

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>步骤 2：创建到现有映像 （普通 OS 或开发环境，如.NET Core、 Node.js 和 Ruby） 相关的 DockerFile

你将需要每个要生成的自定义映像和每个要部署的容器的 DockerFile，因此，如果您的应用程序由一个自定义服务组成，您将需要一个 DockerFile。 但是，如果您的应用程序组成 （如中所示的微服务体系结构） 的多个服务，你将需要一个 Dockerfile，每个服务。

DockerFile 通常放置在你的应用或服务的根文件夹内，并包含所需的命令，这样该 Docker 就知道如何设置和运行该应用程序或服务。 你可以创建 DockerFile 并将其添加到你的项目以及你的代码 (node.js，.NET Core 等)，或者，如果你不熟悉的环境，看一看以下提示。

> [!TIP]
> 可以使用名为的命令行工具[yo docker](https://github.com/Microsoft/generator-docker)，其中搭建基架以选择并添加所需的 Docker 配置文件的语言中的项目中的文件。 基本上，帮助开发人员入门，创建相应的 DockerFile，docker-compose.yml 和其他相关联的脚本，以生成并运行 Docker 容器。 此 yeoman 生成器将提示你使用的一些问题，询问你所选的开发语言和目标容器主机。

![yo docker](./media/image21.png)

例如，图 4-17 显示终端中的两个屏幕快照，在 Windows 中，在 Mac 上，在这两种情况下，运行则 docker，将生成的示例代码项目 （当前.NET Core、 Golang 和 Node.js 用作受支持的语言） 已配置为在上工作Docker 的顶部。

![](./media/image22.PNG)  ![](./media/image23.png)

图 4-17: yo docker 命令在 Windows （左） 和 Mac 上的工具

图 4-18 提供了示例则 docker 后使用你的位置，以将基架的一个现有的.NET Core 项目。

![](./media/image24.PNG)

图 4-18： 则使用现有的.NET Core docker 项目就地

Dockerfile，您可以指定您将使用 （如使用"发件人 microsoft/dotnet:1.0.0-core"） 的基础 Docker 映像。 您通常将生成自定义映像可以从在任何官方存储库获取的基本映像之上[Docker Hub 注册表](https://hub.docker.com/)(如[适用于.NET Core 映像](https://hub.docker.com/r/microsoft/dotnet/)或一个[适用于 Node.js](https://hub.docker.com/_/node/)).

***选项 a:使用现有的官方 Docker 映像***

语言堆栈的官方存储库中使用版本号可确保相同的语言功能 （包括开发、 测试和生产） 的所有计算机上可用。

以下是示例 DockerFile.NET Core 容器：

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

在这种情况下，它适用于 Linux 名为 microsoft/aspnetcore:1.0.1 使用正式的 ASP.NET Core Docker 映像的版本 1.0.1。  有关更多详细信息，请查阅[ASP.NET Core Docker 映像页](https://hub.docker.com/r/microsoft/aspnetcore/)和[.NET Core Docker 映像页](https://hub.docker.com/r/microsoft/dotnet/)。 你还可能正在使用另一可比较的映像，如节点： 4-Node.js，或对于开发语言，可在许多其他预配置的映像的 onbuild [Docker Hub](https://hub.docker.com/explore/)。

在 DockerFile，还需要指示 Docker 侦听 TCP 端口将使用在运行时 （如端口 80）。

有其他行的这样 Docker 就知道如何运行该应用程序可以在具体取决于你使用的，语言/框架 DockerFile 中添加的配置。 例如，你需要使用的入口点行\["dotnet"，"MyCustomMicroservice.dll"\]运行.NET Core 应用程序中，虽然您可以有多个不同版本，具体取决于生成并运行你的服务的方法。 如果你正在使用的 SDK 和 dotnet CLI 生成并运行.NET 应用程序，则将为略有不同。 底部行是入口点行加上其他行将无法为应用程序选择的语言/平台而异。

**详细信息** 有关生成.NET Core 应用程序的 Docker 映像的信息，请转到<https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>。

若要了解有关构建你自己的映像的详细信息，请转到[ https://docs.docker.com/engine/\ 教程/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/)。

**多平台映像存储库**

随着 Windows 容器变得更加普遍，单个存储库可以包含平台变量，如 Linux 和 Windows 映像。 这是一项新功能使得供应商可以使用单个存储库来涵盖多个平台，例如 Docker 中即将推出[microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)存储库，则可以从 DockerHub 注册表。 由于该功能提供处于活动状态，从 Windows 主机拉取此映像会拉取 Windows 变体，而从 Linux 主机拉取同一映像名称会拉取 Linux 变体。

***选项 b:从头开始创建您的基础映像***

您可以从头开始创建您自己的 Docker 基础映像在此所述[一文](https://docs.docker.com/engine/userguide/eng-image/baseimages/)从 Docker。 这是如果您刚开始使用 Docker，则可能不最适合您的方案，但如果你想要设置的基础映像的特定位，您可以执行此操作。

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>步骤 3：创建自定义 Docker 映像中嵌入你的服务

对于每个包含您的应用程序的自定义服务，你将需要创建一个相关的映像。 如果您的应用程序由单个服务或 web 应用的组成，将需要一个映像。

> [!NOTE]
> 时考虑到"外部循环 DevOps 工作流"，图像将通过自动的生成过程以便将该全局环境中创建映像到 Git 存储库 （持续集成） 推送你的源代码时从创建应用源代码。

但是，我们考虑转到该外部循环路由之前，我们需要确保，Docker 应用程序工作正常，以便它们不推送到源代码管理系统 （Git 等） 可能无法正常工作的代码。

因此，每个开发人员首先需要执行整个的内部循环过程，以在本地测试，继续开发直到他们想要推送完整的功能或将更改为源代码管理系统。

若要在本地环境和使用 DockerFile 创建映像，您可以使用 docker 生成命令，如图 4-19 中所示 (还可以运行 docker compose up--生成的应用程序由多个容器/服务)。

![](./media/image25.png)

图 4-19:正在运行的 docker 生成

（可选） 而不是直接运行 docker 生成从项目的文件夹，则第一次可以生成可部署的文件夹具有需要通过运行的 dotnet 发布命令，并运行 docker 生成.NET 库。

在此示例中，这将创建的 Docker 映像名称 cesardl/netcore 端 webapi 微服务使用的 docker： 第一个 (: 首先是一个标记，如特定版本)。 可能需要此步骤中的每个自定义映像需要创建组合 Docker 应用程序与多个容器。

你可以找到现有的映像在本地存储库中 （在开发计算机） 使用 docker 映像命令，如图 4 到 20 中所示。

![](./media/image26.png)

图 4-20:查看现有的映像使用的 docker 映像

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>步骤 4：（可选）生成包含多个服务的组合的 Docker 应用程序时在 docker-compose.yml 中定义服务

使用 docker-compose.yml 文件可定义一组相关服务部署为组合应用程序与下一步的步骤部分所述的部署命令。

您需要创建该文件在主或根解决方案文件夹;它应该类似内容以下 docker-compose.yml 文件：

```yml
version: '2'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

在此特定情况下，此文件定义两个服务： web 服务 （自定义的服务） 和 redis 服务 （受欢迎的缓存服务）。 每个服务将部署为一个容器，因此我们需要为每个使用具体的 Docker 映像。 对于此特定的 web 服务，该映像将需要执行以下操作：

-   中的当前目录中的 DockerFile 生成

-   转发的公开的端口 80 上向主机计算机上的端口 81 容器

-   到 /code 在容器中，使你能够修改代码，而无需重新生成映像可能在主机上装载项目目录

-   Web 服务链接到 redis 服务

Redis 服务使用[最新的公共 redis 映像](https://hub.docker.com/_/redis/)从 Docker 中心注册表中拉取。 [redis](https://redis.io/)是一个非常受欢迎的缓存系统，用于服务器端应用程序。

### <a name="step-5-build-and-run-your-docker-app"></a>步骤 5：生成并运行 Docker 应用

如果您的应用程序具有单个容器，只需通过将其部署到 Docker 主机 （VM 或物理服务器） 运行。 但是，如果您的应用程序由多个服务组成，则需要*compose 它*、 过。 让我们查看不同的选项。

***选项 a:运行单个容器或服务***

可以通过使用 docker 运行命令，如下所示运行 Docker 映像：

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

请注意，对于此特定的部署，我们将会将请求重定向发送到端口 80 到内部端口 5000。 现在，该应用程序侦听的外部端口 80 主机级别。

***选项 b:编写和运行多容器应用程序***

在大多数企业方案中，将多个服务组成的 Docker 应用程序。 对于这些情况下，可以运行该命令的 docker-compose up (图 4-21)，它将使用可能在之前创建的 docker-compose.yml 文件。 运行此命令将部署及其相关容器的所有组合应用程序。

![](./media/image27.png)

图 4-21:运行"docker compose up"命令的结果

在运行 docker 后-compose up，您将部署你的应用程序和其相关的容器到 Docker 主机中，如图 4-22 所示的 VM 表示形式。

![](./media/image28.png)

图 4-22:部署了 Docker 容器的 VM

请注意 docker compose up 和 docker 运行可能已足够用于测试你的容器中开发环境中，但您可能根本不使用它们如果希望使用 Docker 群集和业务流程协调程序，例如 Docker Swarm、 Mesosphere DC/OS 或 Kubernetes若要纵向扩展将。 如果您使用等集群[Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（用于 Docker 的 Windows 和 Mac 自 1.12 版起），您需要部署和测试与其他命令，例如为单个服务，创建 docker 服务，或者后部署多个容器组成的应用，使用 docker compose 捆绑包和 docker 部署 myBundleFile，通过作为堆栈，部署组成的应用，本文中所述[分布式应用程序捆绑包](https://blog.docker.com/2016/06/docker-app-bundle/)从 Docker。

有关[DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/)并[Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment)不同的部署命令和脚本，也会使用。

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>步骤 6：测试 Docker 应用程序 （在本地，本地 CD VM)

根据您的应用程序正在执行什么操作，此步骤会有所不同。

在非常简单.NET Core Web API"Hello World"部署为单个容器或服务，你只需通过提供 DockerFile 中指定的 TCP 端口访问服务。

如果 localhost 未开启，若要导航到你的服务，通过使用此命令为机查找 IP 地址：

docker 计算机 ip*你的容器名称*

在 Docker 主机上，打开浏览器并导航到该站点;图 4-23 所示，您应该看到运行，将应用程序/服务。

![](./media/image29.png)

图 4-23:测试 Docker 应用程序使用 localhost 在本地

请注意，则使用端口 80，但在内部它已被重定向到端口 5000，因为这是它的部署方式使用 docker 运行，如前面所述。

您可以从终端使用 CURL 进行测试。 在 Windows 上的 Docker 安装，默认 IP 是为 10.0.75.1，如下图所示在图 4 到 24 个。

![](./media/image30.png)

图 4-24:通过使用 CURL 在本地测试 Docker 应用程序

**调试在 Docker 上运行的容器**

Visual Studio Code 支持调试 Docker，如果您使用的 Node.js 和其他平台，如.NET Core 容器。

您还可以调试在 Docker 中的.NET Core 容器时使用 Visual Studio 中下, 一节中所述。

**详细信息：** 若要了解有关调试 Node.js Docker 容器的详细信息，请转到<https://blog.docker.com/2016/07/live-debugging-docker/>并[https://blogs.msdn.microsoft.com/\用户\_ed/2016年/02/27 /visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/)。

>[!div class="step-by-step"]
>[上一页](docker-apps-development-environment.md)
>[下一页](visual-studio-tools-for-docker.md)