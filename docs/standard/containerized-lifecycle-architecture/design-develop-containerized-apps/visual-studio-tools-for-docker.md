---
title: Visual Studio Tools for Windows 上的 Docker
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170790"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)

Visual Studio Tools for Docker 开发人员工作流是类似于使用 Visual Studio Code 和 Docker CLI （它基于出现相同的 Docker CLI）。 Visual Studio Tools Docker 可以更容易，若要开始，可以简化此过程中，并且对于生成，提供更高的生产率运行和组合任务。 执行和调试简单的操作，例如通过容器**F5**并**Ctrl**+**F5**。

> [!NOTE]
> 本文适用到 Windows，在 Visual Studio 并不是 Visual Studio for mac。

## <a name="configure-your-local-environment"></a>配置在本地环境

使用 Docker 的 Windows 的最新版本 ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/))，简单的安装程序可以轻松开发 Docker 应用程序。

Visual Studio 2017 中包括 docker 支持。 在此处下载 Visual Studio 2017: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>在 Visual Studio 2017 中使用 Docker 工具

有两个级别的可以向项目添加 Docker 支持。 在.NET Core web 应用程序项目，只是可以添加*Dockerfile*项目，方法是启用 Docker 支持的文件。 下一级别是容器业务流程协调程序支持，这会增加*Dockerfile*到项目 （如果它尚不存在） 和一个*的 docker-compose.yml*解决方案级文件。

**外** > **Docker 支持**并**添加** > **容器业务流程协调程序支持**命令web 应用程序项目的项目节点的右键单击菜单 （或上下文菜单） 上位于**解决方案资源管理器**中图 4-26 所示：

![在 Visual Studio 中添加 Docker 支持菜单选项](media/add-docker-support-menu.png)

图 4-26： 向 Visual Studio 2017 项目添加 Docker 支持

### <a name="add-docker-support"></a>添加 Docker 支持

可以通过选择到现有的.NET Core web 应用程序项目添加 Docker 支持**外** > **Docker 支持**中**解决方案资源管理器**。 您还可以启用 Docker 支持在项目创建期间通过选择**启用 Docker 支持**中**新的 ASP.NET Core Web 应用程序**在单击后打开的对话框**确定**中**新建项目**对话框中，在图 4-27 所示。

![在 Visual Studio 中的新 ASP.NET Core web 应用的启用 Docker 支持](./media/enable-docker-support-visual-studio.png)

图 4-27: Visual Studio 2017 中的项目创建过程中启用 Docker 支持

在添加或启用 Docker 支持，Visual Studio 添加*Dockerfile*到项目文件。

> [!NOTE]
> 启用时 Docker Compose 支持在.NET Framework web 应用程序项目 （不.NET Core web 应用程序项目） 的项目创建期间在图 4-28 所示，还添加容器业务流程协调程序支持。
>
> ![启用 Docker compose 支持.NET Framework web 应用程序项目](media/enable-docker-compose-support.png)

> 图 4-28： 启用 Visual Studio 2017 中的.NET Framework web 应用项目上的 Docker Compose 支持

### <a name="add-container-orchestrator-support"></a>添加容器业务流程协调程序支持

当你想要编写多容器解决方案时，请向项目添加容器业务流程协调程序支持。 添加容器业务流程协调程序支持，请在 Visual Studio 添加*Dockerfile*到项目 （如果它尚不存在），并全局*的 docker-compose.yml*解决方案级文件。 这样就可以运行和调试容器 （整个解决方案） 的一组在同一时间，如果在同一个定义*docker compose.yml*文件。 如果*docker compose.yml*已存在，Visual Studio 只需向其添加的配置代码所需的行。

将容器业务流程支持添加到你的项目后，你将看到添加到项目中的 Dockerfile 和一个**docker compose**添加到解决方案中的文件夹**解决方案资源管理器**中图 4-29 所示：

![在解决方案资源管理器在 Visual Studio 中的 docker 文件](media/docker-support-solution-explorer.png)

图 4-29： 在 Visual Studio 2017 中的解决方案资源管理器中的 Docker 文件

**详细信息：** 有关服务实现和使用的 Visual Studio Tools for Docker 的详细信息，请阅读以下文章：

生成、 调试、 更新和刷新本地 Docker 容器中的应用： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

将 ASP.NET Core Docker 容器部署到容器注册表： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[上一页](docker-apps-inner-loop-workflow.md)
[下一页](set-up-windows-containers-with-powershell.md)