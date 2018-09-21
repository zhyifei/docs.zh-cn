---
title: 使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: af14c92ab27885deec878dc33e7b94035f43e65b
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46516738"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)

使用 Visual Studio Code 和 Docker CLI 时，开发工作流时使用 Visual Studio Tools for Docker 是类似于工作流。 实际上，它基于相同的 Docker CLI，但它是更轻松地开始，可以简化此过程中，并提供了提高工作效率生成、 运行和组合任务。 它还可以执行和调试你通过简单的操作，例如 F5 和 Ctrl + F5 从 Visual Studio 的容器。 通过可选容器业务流程支持，除了能够运行和调试单个容器，可运行和调试容器 （整个解决方案） 的一组在同一时间。 只需在同一个定义的容器*docker compose.yml*解决方案级文件。

## <a name="configuring-your-local-environment"></a>配置在本地环境

与任何.NET 和.NET Core 工作负载安装 Visual Studio 2017 包含 docker 支持。 单独安装 Docker 的 Windows。

使用 Docker 的 Windows 的最新版本，它是比以往要开发 Docker 应用程序的以下参考中所述，安装程序非常简单，因为更容易。

**详细信息：** 若要了解有关安装 Windows 的 Docker 的详细信息，请转到<https://docs.docker.com/docker-for-windows/>。

**详细信息：** 安装 Visual Studio 的说明，请转到[ https://visualstudio.microsoft.com/downloads/ ](https://visualstudio.microsoft.com/downloads/)。

若要查看有关安装 Visual Studio Tools for Docker 的详细信息，请转到<http://aka.ms/vstoolsfordocker>和<https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>。

## <a name="using-docker-tools-in-visual-studio-2017"></a>在 Visual Studio 2017 中使用 Docker 工具

向项目添加 Docker 支持时 （请参阅图 4-26），Visual Studio 将添加*Dockerfile*到项目根目录。

![启用 Visual Studio 2017 项目中的 Docker 解决方案支持](./media/image32.png)

图 4-26： 启用 Visual Studio 2017 项目中的 Docker 解决方案支持

 默认情况下，在 Visual Studio 2017 版本 15.7 或更早版本中添加容器业务流程支持，通过 Docker Compose。 容器业务流程支持是 Visual Studio 2017 版本 15.8 中选择的功能或更高版本，在这种情况下 Docker Compose 和 Service Fabric 支持。

使用 Visual Studio 15.8 和更高版本，可以在每个具有相关联的容器解决方案中添加对多个项目的支持。 中的解决方案或项目节点上右键单击**解决方案资源管理器**，然后选择**添加** > **容器业务流程支持**。  然后选择**Docker Compose**或**Service Fabric**管理容器。

当你选择**Docker Compose**，Visual Studio 在解决方案中添加一个服务部分*的 docker-compose.yml*文件 （或创建文件，如果它们不存在）。 它是轻松地开始编写多容器解决方案;然后可以打开*docker compose.yml*文件，并使用其他功能更新这些值。

此操作将添加所需的配置行代码来*docker compose.yml*解决方案级别的设置。

您还可以启用 Docker 支持在 Visual Studio 2017 中，创建 ASP.NET Core 项目时在图 4-27 所示。

![创建项目时启用 Docker 支持](./media/image33.png)

图 4-27： 启用 Docker 支持创建项目时

向在 Visual Studio 解决方案中添加 Docker 支持后，您还将看到在新的节点树**解决方案资源管理器**使用添加*的 docker-compose.yml*文件，如下图中图 4-28 所示。

![在解决方案资源管理器中现在显示的 docker-compose.yml 文件](./media/image34.PNG)

图 4-28： 中现在显示的 docker-compose.yml 文件**解决方案资源管理器**

可以部署多容器应用程序使用单个*docker-compose.yml*文件在运行时`docker-compose up`; 但是，Visual Studio 会添加它们，一组，以便可以重写值具体取决于环境 （开发与生产） 和执行类型 （发布与调试）。 后面的章节中更好地解释此功能。

您还可以使用 Service Fabric 而不是 Docker Compose 来管理多个容器。 请参阅[教程： 将 Windows 容器中的.NET 应用程序部署到 Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container)。

**详细信息：** 有关服务实现和使用的 Visual Studio Tools for Docker 的详细信息，请阅读以下文章：

生成、 调试、 更新和刷新本地 Docker 容器中的应用： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

将 ASP.NET Core Docker 容器部署到容器注册表： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[上一页](docker-apps-inner-loop-workflow.md)
[下一页](set-up-windows-containers-with-powershell.md)
