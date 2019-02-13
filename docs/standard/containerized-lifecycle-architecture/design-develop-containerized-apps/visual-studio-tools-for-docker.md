---
title: Visual Studio Tools for Windows 上的 Docker
description: 初步了解 Visual Studio 2017 版本 15.7 及更高版本中提供的 Docker 工具。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.custom: vs-dotnet
ms.openlocfilehash: a373a8ebfef605b9845a684d3987355f8841aa1b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219537"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)

使用 Visual Studio Code 和 Docker CLI 时，Visual Studio Tools for Docker 开发工作流是类似于工作流。 实际上，它基于相同的 Docker CLI，但它是更轻松地开始，可以简化此过程中，并提供了提高工作效率生成、 运行和组合任务。 执行和调试简单的操作，例如通过容器**F5**并**Ctrl**+**F5**。 通过可选容器业务流程支持，除了能够运行和调试单个容器，可运行和调试容器 （整个解决方案） 的一组在同一时间。

> [!NOTE]
> 本文适用到 Windows，在 Visual Studio 并不是 Visual Studio for mac。

## <a name="configure-your-local-environment"></a>配置在本地环境

使用 Docker 的 Windows 的最新版本 ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/))，简单的安装程序可以轻松开发 Docker 应用程序。

Visual Studio 2017 中包括 docker 支持。 在此处下载 Visual Studio 2017: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>在 Visual Studio 2017 中使用 Docker 工具

有两个级别的可以向项目添加 Docker 支持。 在.NET Core web 应用程序项目，只是可以添加*Dockerfile*项目，方法是启用 Docker 支持的文件。 下一级别是容器业务流程支持，这会增加*Dockerfile*到项目 （如果它尚不存在） 和一个*的 docker-compose.yml*解决方案级文件。 默认情况下，在 Visual Studio 2017 版本 15.7 或更早版本中添加容器业务流程支持，通过 Docker Compose。 容器业务流程支持是 Visual Studio 2017 版本 15.8 中选择的功能或更高版本，在这种情况下 Docker Compose 和 Service Fabric 支持。

**外** > **Docker 支持**并**添加** > **容器业务流程支持**命令web 应用程序项目的项目节点的右键单击菜单 （或上下文菜单） 上位于**解决方案资源管理器**中图 4-26 所示：

![在 Visual Studio 中添加 Docker 支持菜单选项](media/add-docker-support-menu.png)

图 4-26:向 Visual Studio 2017 项目添加 Docker 支持

### <a name="add-docker-support"></a>添加 Docker 支持

可以通过选择到现有的.NET Core web 应用程序项目添加 Docker 支持**外** > **Docker 支持**中**解决方案资源管理器**。 您还可以启用 Docker 支持在项目创建期间通过选择**启用 Docker 支持**中**新的 ASP.NET Core Web 应用程序**在单击后打开的对话框**确定**中**新建项目**对话框中，在图 4-27 所示。

![在 Visual Studio 中的新 ASP.NET Core web 应用的启用 Docker 支持](./media/enable-docker-support-visual-studio.png)

图 4-27:Visual Studio 2017 中的项目创建过程中启用 Docker 支持

在添加或启用 Docker 支持，Visual Studio 添加*Dockerfile*到项目文件。

> [!NOTE]
> 启用时 Docker Compose 支持在.NET Framework web 应用程序项目 （不.NET Core web 应用程序项目） 的项目创建期间在图 4-28 所示，还添加容器业务流程支持。
>
> ![启用 Docker compose 支持.NET Framework web 应用程序项目](media/enable-docker-compose-support.png)

> 图 4 日至 28 日：启用 Visual Studio 2017 中的.NET Framework web 应用项目上的 Docker Compose 支持

### <a name="add-container-orchestration-support"></a>添加容器业务流程的支持

当你想要编写多容器解决方案时，请向项目添加容器业务流程支持。 这样就可以运行和调试容器 （整个解决方案） 的一组在同一时间，如果在同一个定义*docker compose.yml*文件。

若要添加容器业务流程支持，请右键单击中的解决方案或项目节点**解决方案资源管理器**，然后选择**添加** > **容器业务流程支持**. 然后选择**Docker Compose**或**Service Fabric**管理容器。

将容器业务流程支持添加到你的项目后，你将看到添加到项目中的 Dockerfile 和一个**docker compose**添加到解决方案中的文件夹**解决方案资源管理器**中图 4-29 所示：

![在解决方案资源管理器在 Visual Studio 中的 docker 文件](media/docker-support-solution-explorer.png)

图 4-29:在 Visual Studio 2017 中的解决方案资源管理器中的 docker 文件

如果*docker compose.yml*已存在，Visual Studio 只需向其添加的配置代码所需的行。

## <a name="configure-docker-tools"></a>配置 Docker 工具

从主菜单中，选择**工具** > **选项**，然后展开**容器工具** > **设置**。 显示容器工具设置。

![](./media/visual-studio-docker-tools-options.png)

图 4-30:Docker 工具选项

下表可能会帮助你决定如何设置这些选项。

| name | 默认设置 | 适用于 | 描述 |
| -----|:---------------:|:----------:| ----------- |
| 自动在项目负载上拉取所需的 Docker 图像 | On | Docker Compose | 为了提高性能，加载项目时，Visual Studio 会启动 Docker pull 操作在后台，以便当准备好运行你的代码，该图像已下载或下载过程中。 如果只是加载项目，并浏览代码，您可以关闭此以避免下载不需要的容器映像。 |
| 在后台自动启动容器 | On | Docker Compose | 再次以提高性能，Visual Studio 创建一个容器使用卷装载供当生成并运行你的容器。 如果你想要控制创建容器时，关闭此功能。 |
| 在解决方案上的终止容器自动关闭 | On | Docker Compose | 关闭此功能如果您想要为解决方案之后关闭解决方案或关闭 Visual Studio 继续运行的容器。 |
| 不提示信任 localhost SSL 证书 | Off | ASP.NET Core 2.1 项目 | 如果不信任 localhost SSL 证书，则 Visual Studio 将提示每次运行你的项目，除非选中此复选框。 |

> [!WARNING]
> 如果 localhost SSL 证书不受信任，并选中复选框后，若要禁止显示提示，然后 HTTPS web 请求可能会在你的应用程序或服务中的运行时失败。 在这种情况下，取消选中**不会提示**复选框，会运行你的项目，并指示在提示符下的信任。

**详细信息：** 有关服务实现和使用的 Visual Studio Tools for Docker 的详细信息，请阅读以下文章：

生成、 调试、 更新和刷新本地 Docker 容器中的应用： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

将 ASP.NET Core Docker 容器部署到容器注册表： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
>[上一页](docker-apps-inner-loop-workflow.md)
>[下一页](set-up-windows-containers-with-powershell.md)