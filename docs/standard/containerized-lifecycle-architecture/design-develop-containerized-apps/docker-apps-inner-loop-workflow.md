---
title: Docker 应用的内部循环开发工作流
description: 了解 Docker 应用程序开发的“内部循环”工作流。
ms.date: 02/15/2019
ms.openlocfilehash: ce573546f61b98c2f93e998203497fa949e9efe8
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644858"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Docker 应用的内部循环开发工作流

在触发跨整个 DevOps 周期的外部循环工作流之前，这一切都从每个开发人员的计算机开始，使用其首选语言或平台对应用本身进行编码，并在本地进行测试（图 4-21）。 但在所有情况下，无论选择何种语言、框架或平台，都有一个重要的共同点。 在此特定的工作流中，始终在本地开发和测试 Docker 容器。

![步骤 1 - 代码/运行/调试](./media/image18.png)

图 4-21  。 内部循环开发上下文

Docker 映像的容器或实例将包含以下组件：

- 操作系统选择（例如，Linux 发行版、Windows）

- 开发人员添加的文件（例如，应用二进制文件）

- 配置（例如，环境设置和依赖项）

- 有关 Docker 运行的进程的说明

可以设置利用 Docker 作为进程的内部循环开发工作流（在下一节中介绍）。 请考虑不包括设置环境的初始步骤，因为只需要执行一次操作。

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>使用 Visual Studio Code 和 Docker CLI 在 Docker 容器中构建单个应用

应用由开发人员自己的服务和其他库（依赖项）组成。

图 4-22 显示了构建 Docker 应用时通常需要执行的基本步骤，每个步骤后跟详细说明。

![工作流概述：步骤 1 - 代码，步骤 2 - 编写 Dockerfile，步骤 3 - 创建使用 Dockerfile 定义的映像，步骤 4 - 使用 docker-compose 文件定义服务，步骤 5 - 运行容器或组合式应用，步骤 6 - 测试应用，步骤 7 - 推送以开始外部循环（CI/CD 管道）或继续开发。](./media/image19.png)

**图 4-22**。 使用 Docker CLI 实现 Docker 容器化应用程序生命周期的高级工作流

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>步骤 1：在 Visual Studio Code 中开始编码并创建初始应用/服务基线

开发应用程序的方式与开发不带 Docker 的应用程序的方式类似。 二者的区别在于，在开发过程中，将部署和测试在本地环境中放置的 Docker 容器（如 Linux VM 或 Windows）中运行的应用程序或服务。

**设置本地环境**

使用最新版本的用于 Mac 和 Windows 的 Docker，开发 Docker 应用程序容易得多，因为设置非常简单。

> [!INFORMATION]
>
> 如需设置用于 Windows 的 Docker 的说明，请转到 <https://docs.docker.com/docker-for-windows/>。
>
>如需设置用于 Mac 的 Docker 的说明，请转到 <https://docs.docker.com/docker-for-mac/>。

此外，还需要代码编辑器，以便在使用 Docker CLI 时实际开发应用程序。

Microsoft 提供 Visual Studio Code，它是 Mac、Windows 和 Linux 支持的轻量级代码编辑器，并为 IntelliSense 提供[多种语言的支持](https://code.visualstudio.com/docs/languages/overview)（JavaScript、.NET、Go、Java、Ruby、Python 和大多数现代语言）、[调试](https://code.visualstudio.com/Docs/editor/debugging)、[与 Git 集成](https://code.visualstudio.com/Docs/editor/versioncontrol)和[扩展插件支持](https://code.visualstudio.com/docs/extensions/overview)。 此编辑器是 Mac 和 Linux 开发人员的绝佳选择。 在 Windows 中，还可以使用完整的 Visual Studio 应用程序。

> [!INFORMATION]
>
> 如需了解用于 Windows、Mac 或 Linux 的 Visual Studio Code 的安装说明，请转到 <https://code.visualstudio.com/docs/setup/setup-overview/>。
>
> 如需设置用于 Mac 的 Docker 的说明，请转到 <https://docs.docker.com/docker-for-mac/>。

可以使用 Docker CLI 并使用任何代码编辑器编写代码，但使用带 Docker 扩展的 Visual Studio Code 可以轻松编写工作区中的 `Dockerfile` 和 `docker-compose.yml` 文件。 还可以使用下面的 Docker CLI 从 Visual Studio Code IDE 运行任务和脚本，以执行 Docker 命令。

VS Code 的 Docker 扩展提供以下功能：

- 自动执行 `Dockerfile` 和 `docker-compose.yml` 文件生成

- `docker-compose.yml` 和 `Dockerfile` 文件的语法突出显示和悬停提示

- `Dockerfile` 和 `docker-compose.yml` 文件的 IntelliSense（完成）

- `Dockerfile` 文件的 Linting（错误和警告）

- 最常用的 Docker 命令的命令面板 (F1) 集成

- 用于管理映像和容器的 Explorer 集成

- 将映像从 DockerHub 和 Azure 容器注册表部署到 Azure 应用服务

要安装 Docker 扩展，请按 Ctrl+Shift+P，键入 `ext install`，然后运行安装扩展命令以打开市场扩展列表。 接下来，键入“docker”，对结果进行筛选，然后选择 Docker 支持扩展，如下图 4-23 所示  。

![VS Code 的 Docker 扩展视图。](./media/image20.png)

图 4-23  。 在 Visual Studio Code 中安装 Docker 扩展

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>步骤 2：创建与现有映像相关的 DockerFile（普通 OS 或 .NET Core、Node.js 和 Ruby 等开发环境）

需要为每个自定义映像构建 `DockerFile`，并且每个容器都需要部署。 如果应用由单个自定义服务组成，则需要一个 `DockerFile`。 但是，如果应用由多个服务组成（如微服务体系结构中所示），则每个服务需要一个 `Dockerfile`。

`DockerFile` 通常放在应用或服务的根文件夹中且包含所需命令，以便 Docker 知道如何设置和运行该应用或服务。 可以创建 `DockerFile` 并将其与代码（node.js、.NET Core 等）一起添加到项目中。或者，如果你是初次接触环境，请查看以下提示。

> [!TIP]
>
> 在使用与 Docker 容器相关的 `Dockerfile` 和 `docker-compose.yml` 文件时，可以使用 Docker 扩展来提供指导。 最终，可能无需使用此工具，即可编写这些类型的文件，但使用 Docker 扩展是一个很好的起点，可以加快学习曲线。

在图 4-24 中，可以看到如何使用 VS Code 的 Docker 扩展添加 docker-compose 文件。

![VS Code 的 Docker 扩展控制台视图。](./media/image24.png)

图 4-24  。 使用“将 Docker 文件添加到工作区命令”添加 Docker 文件 

添加 DockerFile 时，可以指定要使用的 Docker 映像（如使用 `FROM mcr.microsoft.com/dotnet/core/aspnet`）。 通常会在 [Docker Hub 存储库](https://hub.docker.com/)中的任何官方存储库（如 [.NET Core 的映像](https://hub.docker.com/_/microsoft-dotnet-core/)或 [Node.js](https://hub.docker.com/_/node/) 的映像）中获得的基础映像上构建自定义映像。

***使用现有的官方 Docker 映像***

使用带版本号的语言堆栈的官方存储库，可确保在所有计算机（包括开发、测试和生产）上都可以使用相同的语言功能。

以下示例显示 .NET Core 容器的示例 DockerFile：

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

在此情况下，该映像以官方 ASP.NET Core Docker 映像的版本 2.2（适用于 Linux 和 Windows 的多体系结构）为基础，依据此行 `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`。 （有关此主题的详细信息，请参阅 [ASP.NET Core Docker 映像](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)页和 [.NET Core Docker 映像](https://hub.docker.com/_/microsoft-dotnet-core/)页。）

在 DockerFile 中，还可以指示 Docker 侦听将在运行时使用的 TCP 端口（如端口 80）。

可在 Dockerfile 中指定其他配置设置，具体取决于使用的语言和框架。 例如，带有 `["dotnet", "MySingleContainerWebApp.dll"]` 的 `ENTRYPOINT` 行指示 Docker 运行 .NET Core 应用程序。 如果使用 SDK 和 .NET Core CLI (`dotnet CLI`) 来生成和运行 .NET 应用程序，则此设置会有所不同。 此处关键在于 ENTRYPOINT 行和其他设置根据为应用程序选择的语言和平台而有所不同。

> [!INFORMATION]
>
> 有关为 .NET Core 应用程序生成 Docker 映像的详细信息，请转到 <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>。
>
> 如需了解有关构建自己的映像的详细信息，请转到 <https://docs.docker.com/engine/tutorials/dockerimages/>。

使用多体系结构映像存储库 

存储库中的单个映像名称可包含平台变量，如 Linux 映像和 Windows 映像。 借助此功能，Microsoft（基础映像创建者）等供应商可创建涵盖多个平台（即 Linux 和 Windows）的单个存储库。 例如，Docker Hub 注册表中提供的 [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 存储库使用相同的映像名称为 Linux 和 Windows Nano Server 提供支持。

从 Windows 主机拉取 [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) 映像时，也会拉取 Windows 变体，并且从 Linux 主机拉取同一映像名称时，也会拉取 Linux 变体。

***从头开始创建基础映像***

可以从头开始创建自己的 Docker 基础映像，如 Docker 中的[文章](https://docs.docker.com/engine/userguide/eng-image/baseimages/)中所述。 如果刚开始使用 Docker，此方案可能不是最佳方案，但如果想为自己的基础映像设置特定位，则可采用此方案。

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>步骤 3：创建将服务嵌入其中的自定义 Docker 映像

需要为构成应用的每个自定义服务创建相关映像。 如果应用由单个服务或 Web 应用组成，则只需创建单个映像即可。

> [!NOTE]
>
> 考虑“外部循环 DevOps 工作流”时，只要将源代码推送到 Git 存储库（持续集成），就会通过自动构建过程创建映像，因此将在全局环境中从源代码创建映像。
>
> 但在考虑采用外部循环路由之前，需要确保 Docker 应用程序实际上正常工作，这样它们就不会将可能无法正常工作的代码推送到 Git 等源代码管理系统。
>
> 因此，每个开发人员首先需要执行整个内部循环过程，才能在本地进行测试并继续开发，直到他们想要推送完整的功能或更改为源代码管理系统。

要在本地环境中创建映像并使用 DockerFile，可以使用 docker build 命令，如图 4-25 所示（对于由多个容器/服务组成的应用程序，也可以运行 `docker-compose up --build`）。

![Docker-compose 构建的控制台输出，其中显示映像下载进度。](./media/image25.png)

图 4-25  。 运行 docker build

可以先使用运行 `dotnet publish` 命令生成一个包含所需 .NET 库的可部署文件夹，然后运行 `docker build`，而不是直接从项目文件夹运行 `docker build`（可选）。

此示例创建名为 `cesardl/netcore-webapi-microservice-docker:first` 的 Docker 映像（`:first` 是标记，类似于特定版本）。 可为需要为具有多个容器的组合 Docker 应用程序创建的每个自定义映像执行此步骤。

使用 docker images 命令可查找本地存储库（开发计算机）中的现有映像，如图 4-26 所示。

![命令 docker 映像的控制台输出，其中显示现有映像。](./media/image26.png)

**图 4-26**。 使用 docker 映像查看现有映像

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>步骤 4：在构建具有多服务的组合 Docker 应用时，在 docker-compose.yml 中定义服务

借助 `docker-compose.yml` 文件，可以使用下一步中介绍的部署命令定义要部署为组合应用程序的一组相关服务。

在主解决方案文件夹或根解决方案文件夹中创建该文件；该文件的内容应与此 `docker-compose.yml` 文件中显示的内容类似：

```yml
version: '3.4'
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

在此特定情况下，此文件定义两个服务：Web 服务（自定义的服务）和 redis 服务（常用缓存服务）。 每项服务都将作为容器部署，因此需要为每个服务使用具体的 Docker 映像。 对于此特定 Web 服务，映像需要执行以下操作：

- 从当前目录中的 DockerFile 构建

- 将容器上的公开端口 80 转接到主机上的端口 81

- 将主机上的项目目录挂载到容器中的 /code，无需重新生成映像，即可修改代码

- 将 Web 服务链接到 redis 服务

Redis 服务使用从 Docker Hub 注册表中拉取的[最新公共 redis 映像](https://hub.docker.com/_/redis/)。 [redis](https://redis.io/) 是服务器端应用程序的常用缓存系统。

### <a name="step-5-build-and-run-your-docker-app"></a>步骤 5：生成 Docker 应用并运行该应用

如果应用只有一个容器，只需将其部署到 Docker 主机（VM 或物理服务器），即可运行该应用。 但是，如果应用由多个服务组成，则需要进行编写  。 接下来查看不同的选项。

***选项 A：运行单个容器或服务***

使用 docker 运行命令，即可运行 Docker 映像，如下所示：

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

对于此特定部署，我们会将发送到端口 80 的请求重定向到内部端口 5000。 现在，应用程序将侦听主机级别的外部端口 80。

***选项 B：编写和运行多容器应用程序***

在大多数企业场景中，Docker 应用程序将由多个服务组成。 对于这些情况，可以运行 `docker-compose up` 命令（图 4-27），该命令将使用上述创建的 docker-compose.yml 文件。 运行此命令将使用其所有相关容器部署组合式应用程序。

![来自 docker-compose up 命令的控制台输出。](./media/image27.png)

**图 4-27**。 运行“docker-compose up”命令的结果

运行 `docker-compose up` 后，（如图 4-28 所示）在 VM 表示形式中将应用程序及其相关容器部署到 Docker 主机中。

![运行多容器应用程序的 VM。](./media/image28.png)

**图 4-28**。 部署了 Docker 容器的 VM

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>步骤 6：在本地（在本地 CD VM 中）测试 Docker 应用程序

这一步骤会因应用的用途而有所不同。

在部署为单个容器或服务的简单 .NET Core Web API“Hello World”中，只需提供 DockerFile 中指定的 TCP 端口，即可访问该服务。

如果未启用 localhost，要导航到服务，请使用以下命令查找计算机的 IP 地址：

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

在 Docker 主机上，打开浏览器并导航到该站点，应看到应用/服务正在运行（如图 4-29 所示）。

![来自 localhost/API/值的响应的浏览器视图。](./media/image29.png)

**图 4-29**。 使用 localhost 在本地测试 Docker 应用程序

请注意，它将使用端口 80，但在内部它被重定向到端口 5000，因为这是使用 `docker run` 部署它的方式，如前所述。

可以使用来自终端的 CURL 对其进行测试。 在安装在 Windows 上的 Docker 中，默认 IP 为 10.0.75.1（如图 4-30 所示）。

![通过 curl 获取 http://10.0.75.1/API/values 的控制台输出](./media/image30.png)

**图 4-30**。 使用 CURL 在本地测试 Docker 应用程序

**调试在 Docker 上运行的容器**

如果使用的是 Node.js 和 .NET Core 容器等其他平台，则 Visual Studio Code 支持调试 Docker。

使用 Visual Studio for Windows or Visual Studio for Mac 时，还可以在 Docker 中调试 .NET Core 或 .NET Framework 容器，如下一节所述。

> [!INFORMATION]
>
> 如需了解有关调试 Node.js Docker 容器的详细信息，请转到 <https://blog.docker.com/2016/07/live-debugging-docker/> 和 <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>。

>[!div class="step-by-step"]
>[上一页](docker-apps-development-environment.md)
>[下一页](visual-studio-tools-for-docker.md)
