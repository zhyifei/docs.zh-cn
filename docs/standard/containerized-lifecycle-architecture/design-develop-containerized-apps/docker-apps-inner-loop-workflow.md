---
title: 对于 Docker 应用程序的内部循环开发工作流
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: cda9aa77ca033dced8b6b30538f19f28a5fa63a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579205"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>对于 Docker 应用程序的内部循环开发工作流

触发跨越整个 DevOps 外部循环工作流之前重启，所有它开始每个开发人员的计算机上，编码在应用程序、 使用其首选的语言或平台，以及本地测试 (图 4-14)。 但在这些情况下，你将具有非常重要的一点共同点，无论你选择何种语言、 框架或平台。 在此特定的工作流，你始终开发和测试 Docker 容器，但却在本地。

![](./media/image18.png)

图 4-14： 内部循环开发上下文

容器或 Docker 映像的实例将包含这些组件：

-   操作系统选择 （例如，一种 Linux 分发或 Windows）

-   由开发人员 （例如，应用程序二进制文件） 添加文件

-   配置 （例如，环境设置及依赖关系）

-   流程的说明，若要运行的 Docker

你可以将作为进程 （在下一部分中所述） 使用 Docker 的内部循环开发工作流设置。 考虑设置环境的初始步骤不包括在内，因为你需要为此，只需一次。

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>生成使用 Visual Studio Code 和 Docker CLI Docker 容器中的单个应用程序

应用程序从你自己的服务以及其他库 （依赖关系） 组成。

图 4-15 显示通常需要在生成 Docker 应用程序，每个步骤的详细说明后跟时执行的基本步骤。

![](./media/image19.png)

图 4-15： 使用 Docker CLI Docker 容器化应用程序生命周期的高级工作流

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>步骤 1： 使用 Visual Studio Code 中开始编码，并创建初始应用程序/服务基线

开发应用程序的方法是不 Docker 工作方式非常相似。 区别是，在开发时，你部署和测试您的应用程序或服务在放置在本地环境 （如 Windows 或 Linux VM） 的 Docker 容器内运行。

**设置本地环境**

适用于 Mac 和 Windows 的 Docker 的最新版本，它是比以往若开发 Docker 应用程序，并且安装程序直接。

**详细信息** 有关用于 Windows 的 Docker 设置的说明，请转到[ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/)。

有关设置适用于 Mac 的 Docker 的说明，请转到<https://docs.docker.com/docker-for-mac/>。

此外，你将需要代码编辑器，以便您实际上可以开发你的应用程序时使用 Docker CLI。

Microsoft 提供了 Visual Studio 代码，这是在 Mac、 Windows 和 Linux 上支持并提供包含 IntelliSense 的轻量代码编辑器[处理很多语言支持](https://code.visualstudio.com/docs/languages/overview)(JavaScript、.NET、 转到、 Java、 Ruby、 Python 和大多数现代的语言），[调试](https://code.visualstudio.com/Docs/editor/debugging)，[集成 Git 与](https://code.visualstudio.com/Docs/editor/versioncontrol)和[扩展支持](https://code.visualstudio.com/docs/extensions/overview)。 此编辑器是非常适合于 Mac 和 Linux 的开发人员。 在 Windows 中，你还可以使用完整的 Visual Studio 应用程序。

**详细信息** 安装 Visual Studio for Windows、 Mac 或 Linux 的说明，请转到[ http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/ ](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/)。

您可以使用 Docker CLI 和写入你的代码使用任何代码编辑器中，但如果你使用 Visual Studio 代码，它使用户可以轻松对作者 Dockerfile 和 docker-compose.yml 文件在工作区中。 此外，你可以从 IDE 它会提示用户可以使用下方的 Docker CLI 的详细的操作运行的脚本运行 Visual Studio Code 任务。

通过扩展，你将需要安装提供了 visual Studio 代码。 为此，请按 Ctrl + Shift + P，键入**ext 安装**，然后运行扩展： 安装的扩展插件命令以显示应用商店扩展列表。 接下来，键入**docker**要筛选的结果，然后选择 Dockerfile 和 Docker Compose 文件 (yml) 支持扩展，如下图所示图 4-16。

![](./media/image20.png)

图 4-16： 在 Visual Studio Code 中安装 Docker 扩展

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>步骤 2： 创建与现有映像 （纯 OS 或开发人员环境类似于.NET Core、 Node.js 和 Ruby） 相关的 DockerFile

你将需要每个要生成的自定义图像和每个要部署的容器的 DockerFile，因此，如果你的应用程序组成单个自定义服务，你将需要单个 DockerFile。 但是，如果你的应用程序组成 （如所示的微服务体系结构） 的多个服务，你将需要每个服务的一个 Dockerfile。

DockerFile 通常放置在你的应用或服务的根文件夹内，并包含所需的命令，这样该 Docker 就知道如何设置和运行该应用程序或服务。 你可以创建 DockerFile 并将其添加到你的项目以及你的代码 (node.js，.NET Core 等)，或者，如果你不熟悉的环境，看一看以下提示。

> [!TIP]
> 你可以使用命令行工具调用[则 docker](https://github.com/Microsoft/generator-docker)，其中的基架你项目中，选择并添加所需的 Docker 配置文件的语言中的文件。 基本上，以帮助开发人员入门，它创建相应的 DockerFile，docker-compose.yml 和其他关联的脚本，以生成并运行你的 Docker 容器。 此 yeoman 生成器将提示你使用几个问题，要求你所选的开发语言和目标容器主机。

![则 docker](./media/image21.png)

例如，图 4-17 显示终端中的两个屏幕快照，在 Windows 中，在 Mac 上，在这两种情况下，运行则 docker，将生成的示例代码项目 （当前.NET Core、 Golang 和 Node.js 用作受支持的语言） 已配置为在上工作Docker 的顶部。

![](./media/image22.PNG)  ![](./media/image23.png)

图 4-17： 则 docker 命令在 Windows （左） 和在 Mac 上的工具

图 4-18 提供了示例则 docker 后使用你的位置，以将基架的一个现有的.NET Core 项目。

![](./media/image24.PNG)

图 4-18： 则使用现有的.NET Core docker 项目就地

从此 DockerFile，你指定哪些基本的 Docker 映像，你将使用 （如使用"发件人 microsoft/dotnet:1.0.0-core"）。 你通常将生成你在你可以从在任何官方存储库获取的基本映像之上的自定义映像[Docker Hub 注册表](https://hub.docker.com/)(如[.NET Core 的映像](https://hub.docker.com/r/microsoft/dotnet/)或一个[for Node.js](https://hub.docker.com/_/node/)).

***选项 a： 使用现有的官方 Docker 映像***

使用版本号语言堆栈的官方存储库，可确保相同的语言功能是可用 （包括开发、 测试和生产） 的所有计算机上。

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

DockerFile，还需要指示 Docker 侦听到将在运行时 （如端口 80） 使用的 TCP 端口。

有其他行的这样 Docker 就知道如何运行该应用程序可以在具体取决于你使用的，语言/框架 DockerFile 中添加的配置。 例如，你需要使用的入口点行\["dotnet"，"MyCustomMicroservice.dll"\]运行.NET Core 应用程序中，虽然您可以有多个不同版本，具体取决于生成并运行你的服务的方法。 如果你正在使用的 SDK 和 dotnet CLI 生成并运行.NET 应用程序，则将为略有不同。 底部行是入口点行加上其他行将无法为应用程序选择的语言/平台而异。

**详细信息** 有关构建.NET Core 应用程序的 Docker 映像的信息，请转到<https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>。

若要了解有关生成你自己的映像的详细信息，请转到[ https://docs.docker.com/engine/\教程/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/)。

**多平台映像存储库**

当 Windows 容器变得更为普遍，到单个存储库可以包含平台的不同版本，如的 Linux 和 Windows 映像。 这是即将在使供应商可以使用单个存储库来涵盖多个平台，例如的 Docker 中的新功能[microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)存储库，则可以从 DockerHub 注册表。 如功能处于活动状态时，从 Windows 主机提取此映像将请求的 Windows 变体，而从 Linux 主机提取相同的映像名称将请求 Linux 变体。

***选项 b： 创建您从零开始的基础映像***

你可以从头开始创建你自己 Docker 的基本映像这中所述[文章](https://docs.docker.com/engine/userguide/eng-image/baseimages/)从 Docker。 这是如果您刚开始使用 Docker，则可能不适合你的方案，但如果你想要设置自己的基本映像的特定位，你可以执行此操作。

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>步骤 3： 创建自定义 Docker 映像中嵌入你的服务

对于每个自定义服务，它包含你的应用程序，你将需要创建相关的映像。 如果你的应用程序进行的单个服务或 web 应用程序，你将需要单个映像。

> [!NOTE]
> 时考虑到"外部循环 DevOps workflow"，图像将创建由自动的生成过程以便将该全局环境中创建映像到 Git 存储库 （持续集成） 推送你的源代码时从你源代码。

但是，我们考虑转到该外部循环路由之前，我们需要确保该 Docker 应用程序实际正常工作，以便它们不推送到源代码管理系统 （Git 等） 可能无法正常工作的代码。

因此，每个开发人员首先需要为整个的内部循环过程，以本地测试，并在继续开发直到他们想要推送完整的功能或将更改为源代码管理系统。

若要在本地环境和使用 DockerFile 创建映像，你可以使用 docker 生成命令，在图 4-19 中所示 (你还可以运行 docker compose 向上-生成适用于由多个容器/服务的应用程序)。

![](./media/image25.png)

图 4-19： 运行 docker 生成

（可选） 而不是直接运行 docker 生成从项目的文件夹，则第一次可以生成可部署文件夹与通过使用运行的 dotnet 将发布命令，以及然后运行 docker 生成所需的.NET 库。

在此示例中，这将创建的 Docker 映像名称 cesardl/netcore webapi-微服务构成的 docker： 第一个 (: 首先是一个标记，如特定版本)。 你可以执行每个自定义映像与多个容器的 Docker 应用程序由你需要创建此步骤。

你可以找到现有的映像在本地存储库 （你的开发计算机） 使用 docker 映像命令，在图 4-20 中所示。

![](./media/image26.png)

图 4-20： 查看现有的映像使用 docker 映像

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>步骤 4: （可选） 定义中 docker-compose.yml 生成包含多个服务的组合的 Docker 应用程序时你的服务

与 docker-compose.yml 文件可以定义一组相关的服务，若要部署为一个由应用程序使用部署命令下, 一步的步骤节中所述。

你需要创建该文件在你 main 中的或根解决方案文件夹;它应该类似内容以下 docker-compose.yml 文件：

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

在此特定情况下，此文件定义两个服务： web 服务 （你的自定义服务） 和 redis 服务 （常用缓存服务）。 将作为容器，部署每个服务，因此我们需要使用每个具体的 Docker 映像。 对于此特定的 web 服务，映像将需要执行以下操作：

-   中的当前目录中 DockerFile 生成

-   转发的公开的端口 80 容器主机上的端口 81 上

-   使你能够修改代码而无需重新生成映像的容器内的 /code 到主机上装载项目目录

-   链接到 redis 服务的 web 服务

Redis 服务使用[最新的公共 redis 映像](https://hub.docker.com/_/redis/)从 Docker Hub 注册表中提取。 [redis](https://redis.io/)是一个非常受欢迎的缓存系统，用于服务器端应用程序。

### <a name="step-5-build-and-run-your-docker-app"></a>步骤 5： 生成并运行你的 Docker 应用

如果你的应用程序仅单个容器，你只需通过将其部署到你的 Docker 主机 （VM 或物理服务器） 中运行它。 但是，如果你的应用程序由多个服务组成，则需要*拆分组合*也。 我们来看的不同选项。

***选项 a： 运行单个容器或服务***

你可以通过使用 docker 运行命令，如下所示运行 Docker 映像：

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

请注意，对于此特定的部署，我们将会重定向请求发送到端口 80 到内部端口 5000。 现在，应用程序正在侦听的外部端口 80 主机级别。

***选项 b: Compose 和运行多个容器应用程序***

在大多数的企业方案中，Docker 应用程序将组成多个服务。 对于这些情况下，你可以运行命令 docker compose 向上 (图 4-21)，它将使用先前可能已创建 docker-compose.yml 文件。 运行此命令将部署一个由具有其所有相关容器应用程序。

![](./media/image27.png)

图 4-21： 的运行"docker-撰写向上"命令的结果

在运行 docker 后-向上撰写，你将部署你的应用程序和其相关的容器到 Docker 主机中, 所示在图 4-22，VM 表示形式。

![](./media/image28.png)

图 4-22: VM 与部署的 Docker 容器

请注意 docker-撰写向上和 docker 运行可能足够用于测试你的容器在开发环境中，但你可能根本不使用它们如果你预期使用 Docker 群集和 orchestrators 喜欢 Docker Swarm、 Mesosphere DC/OS 或 Kubernetes为了能够向上扩展。 如果你使用的群集，例如[Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（在用于 Windows 的 Docker 和 Mac 自之后可用版本 1.12），你需要部署和测试与其他命令，例如 docker 服务创建为单个服务，或者如果已部署应用程序组成几个容器，使用 docker compose 捆绑和 docker 通过文章中所述，作为堆栈，部署由应用程序部署 myBundleFile，[分布式应用程序捆绑包](https://blog.docker.com/2016/06/docker-app-bundle/)从 Docker。

有关[DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/)和[Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment)你会使用不同的部署命令和脚本，以及。

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>步骤 6： 测试 Docker 应用程序 （在本地，你的本地 CD VM)

此步骤根据你的应用程序正在执行什么操作会有所不同。

在非常简单.NET Core Web API"Hello World"部署为单个容器或服务，你只需通过提供 DockerFile 中指定的 TCP 端口访问服务。

如果 localhost 未打开，以导航到你的服务，则使用此命令的 IP 地址查找机：

docker 机 ip*你的容器名称*

在 Docker 主机上，打开浏览器并导航到该站点;图 4-23 所示，你应该看到你的应用程序/服务正在运行、。

![](./media/image29.png)

图 4-23： 测试本地使用 localhost Docker 应用程序

请注意，则使用端口 80，但它已在内部重定向到端口 5000，因为这是它的部署方式使用 docker 运行，如前面所述。

你可以通过从终端使用 CURL 来测试此。 在 Windows 上的 Docker 安装，默认 IP 是 10.0.75.1，如下图所示图 4-24。

![](./media/image30.png)

图 4-24： 通过使用 CURL 在本地测试 Docker 应用程序

**调试在 Docker 上运行的容器**

Visual Studio Code 支持调试 Docker，如果你使用 Node.js 和其他平台，如.NET Core 容器。

你还可以调试在 Docker 中的.NET Core 容器时使用 Visual Studio 中下, 一节中所述。

**详细信息：** 若要了解有关调试 Node.js Docker 容器的详细信息，请转到<https://blog.docker.com/2016/07/live-debugging-docker/>和[ https://blogs.msdn.microsoft.com/\ 用户\_ed/2016年/02/27 /visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/)。


>[!div class="step-by-step"]
[以前] (docker-应用程序的开发-environment.md) [下一步] (visual-studio 的工具的对于-docker.md)
