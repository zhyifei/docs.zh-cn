---
title: Windows 上的 Visual Studio Tools for Docker
description: 了解 Visual Studio 2017 15.7 版及更高版本中可用的 Docker 工具。
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644653"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>在 Windows 上的 Visual Studio 2017 中使用 Docker 工具

使用 Visual Studio 2017 15.7 版及更高版本中附带的 Docker 工具的开发人员工作流与使用 Visual Studio Code 和 Docker CLI（事实上，它在同一 Docker CLI 基础上构建）类似，但前者更容易上手，因为它简化了流程并提高了构建、运行和创建任务的工作效率。 还可以通过 Visual Studio 中常用的 `F5` 和 `Ctrl+F5` 键运行和调试容器。 如果在解决方案级别的同一 `docker-compose.yml` 文件中定义其容器，甚至可以调试整个解决方案。

## <a name="configure-your-local-environment"></a>配置本地环境

使用最新版本的用于 Windows 的 Docker，开发 Docker 应用程序容易得多，因为设置非常简单，如以下参考资料中所述。

> [!TIP]
> 要了解有关安装用于 Windows 的 Docker 的详细信息，请转到 (<https://docs.docker.com/docker-for-windows/>)。

## <a name="docker-support-in-visual-studio-2017"></a>Visual Studio 2017 中的 Docker 支持

可以将两个级别的 Docker 支持添加到项目中。 在 ASP.NET Core 项目中，启用 Docker 支持，即可将 `Dockerfile` 文件添加项目中。 下一级是容器业务流程支持，它会向项目添加解决方案级别的 `Dockerfile`（如果它尚不存在）和 `docker-compose.yml` 文件。 默认情况下，在 Visual Studio 2017 15.0 到 15.7 版中添加了通过 Docker Compose 支持的容器业务流程支持。 容器业务流程支持是 Visual Studio 2017 15.8 版或更高版本中的一个可选功能。 15.8 版及更高版本支持 Docker Compose 和 Service Fabric。

“添加”>“Docker 支持”和“添加”>“容器业务流程协调程序支持”命令位于“解决方案资源管理器”中 ASP.NET Core 项目的项目节点的右键单击菜单（或上下文菜单）上，如图 4-31 所示    ：

![Visual Studio 中的“添加 Docker 支持”菜单选项](./media/add-docker-support-menu.png)

**图 4-31**。 向 Visual Studio 2017 项目添加 Docker 支持

### <a name="add-docker-support"></a>添加 Docker 支持

在“解决方案资源管理器”中选择“添加” > “Docker 支持”，即可向现有 ASP.NET Core 项目添加 Docker 支持    。 在项目创建期间，在“新建项目”对话框中单击“确定”后打开的“新建 ASP.NET Core Web 应用程序”对话框中选择“启用 Docker 支持”，也可以启用 Docker 支持（如图 4-32 所示）     。

![在 Visual Studio 中为新的 ASP.NET Core Web 应用启用 Docker 支持](./media/enable-docker-support-visual-studio.png)

**图 4-32**。 在 Visual Studio 2017 中创建项目期间启用 Docker 支持

添加或启用 Docker 支持时，Visual Studio 会向项目添加 Dockerfile 文件  。

> [!NOTE]
> 如图 4-33 所示，在项目创建期间为 ASP.NET 项目（.NET Framework，而不是 .NET Core 项目）启用 Docker Compose 支持时，还会添加容器业务流程支持。

![为 ASP.NET 项目启用 Docker Compose 支持](media/enable-docker-compose-support.png)

**图 4-33**。 为 Visual Studio 2017 中的 ASP.NET 项目启用 Docker Compose 支持

### <a name="add-container-orchestration-support"></a>添加容器业务流程支持

想要构建多容器解决方案时，请为项目添加容器业务流程支持。 这样就可以同时运行和调试一组容器（整个解决方案）（如果已在同一个 docker-compose.yml 文件中定义这些容器  ）。

要添加容器业务流程支持，请右键单击“解决方案资源管理器”中的解决方案或项目节点，然后选择“添加”>“容器业务流程支持”   。 然后，选择“Docker Compose”或“Service Fabric”以管理容器   。

向项目添加容器业务流程支持后，会看到添加到项目的 Dockerfile 文件以及添加到“解决方案资源管理器”中的某个解决方案的 docker-compose 文件夹，如图 4-34 所示   ：

![Visual Studio 解决方案资源管理器中的 Docker 文件](media/docker-support-solution-explorer.png)

**图 4-34**。 Visual Studio 2017 解决方案资源管理器中的 Docker 文件

如果 docker-compose.yml  已存在，Visual Studio 只需向其添加配置代码所需的行。

## <a name="configure-docker-tools"></a>配置 Docker 工具

从主菜单中，选择“工具”>“选项”，然后展开“容器工具”>“设置”   。 随即出现容器工具设置。

![Visual Studio Docker 工具选项包括：“在项目加载时自动拉取所需的 Docker 映像”、“在后台自动启动容器”、“在解决方案关闭时自动终止容器”以及“不提示需要信任 SSL 证书”。](./media/visual-studio-docker-tools-options.png)

**图 4-35**。 Docker 工具选项

下表可帮助确定如何设置这些选项。

| name | 默认设置 | 适用于 | 说明 |
| -----|:---------------:|:----------:| ----------- |
| 在项目加载时自动拉取所需的 Docker 映像 | On | Docker Compose | 为了在加载项目时提高性能，Visual Studio 将在后台启动 Docker 拉取操作，以便在准备好运行代码时，映像已下载或正在下载。 如果只需加载项目和浏览代码，可以将其关闭，以避免下载不需要的容器映像。 |
| 在后台自动启动容器 | On | Docker Compose | 同样，为了提高性能，Visual Studio 会在构建和运行容器时创建卷装载随时可用的容器。 如果要控制创建容器的时间，请将其关闭。 |
| 在解决方案关闭时自动终止容器 | On | Docker Compose | 如果希望解决方案的容器在关闭解决方案或关闭 Visual Studio 后继续运行，请将其关闭。 |
| 不提示需要信任 localhost SSL 证书 | Off | ASP.NET Core 2.2 项目 | 如果 localhost SSL 证书不受信任，则每次运行项目时 Visual Studio 都会提示，除非选中此复选框。 |

> [!WARNING]
> 如果 localhost SSL 证书不受信任且选中该框以禁止出现提示，则 HTTPS Web 请求可能会在应用或服务中在运行时失败。 在这种情况下，请取消选中“不提示”复选框，运行项目并在提示时指示信任  。

> [!TIP]
> 有关服务实现以及 Visual Studio Tools for Docker 用法的更多详细信息，请阅读以下文章：
>
>在本地 Docker 容器中调试应用：<https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>使用 Visual Studio 将 ASP.NET 容器部署到容器注册表：<https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[上一页](docker-apps-inner-loop-workflow.md)
>[下一页](set-up-windows-containers-with-powershell.md)
