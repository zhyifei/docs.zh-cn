---
title: 使用 Visual Studio Tools for Docker (在 Windows 上的 Visual Studio)
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: facc295399a7471edfd3e59eb1cc0e90f01ef11b
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104887"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>使用 Visual Studio Tools for Docker (在 Windows 上的 Visual Studio)

开发人员工作流时使用 Visual Studio 工具，使用 Visual Studio Code 和 Docker CLI 时，Docker 为类似于工作流 （事实上，它基于相同的 Docker CLI），但它可以更轻松地开始，可以简化过程，并可以提供更高工作效率的生成，运行，并构建任务。 它也是可以执行并调试 F5 和 Ctrl + F5 从 Visual Studio 之类的简单操作通过你的容器。 更多，与 Visual Studio 2017，除了能够运行和调试为一个容器，你还可以运行和调试一组的容器 （整个解决方案） 在同一时间如果定义了解决方法级别的相同 docker-compose.yml 文件中。

## <a name="configuring-your-local-environment"></a>配置你的本地环境

用于 Windows 的 Docker 的最新版本，它是比以往来开发 Docker 应用程序中的以下引用所述，安装程序非常简单，因为更容易。

**详细信息：** 若要了解有关安装用于 Windows 的 Docker 的详细信息，请转到<https://docs.docker.com/docker-for-windows/>。

如果你在使用 Visual Studio 2015，你必须具有 Update 3 或更高版本以及 Visual Studio Tools for Docker。

**详细信息：** 安装 Visual Studio 的说明，请转到[https://visualstudio.microsoft.com/\产品/vs-2015年-产品的版本](https://visualstudio.microsoft.com/products/vs-2015-product-editions)。

若要查看更多有关安装 Visual Studio Tools for Docker，请转到<http://aka.ms/vstoolsfordocker>和<https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>。

如果你使用 Visual Studio 2017 年 1，则已包含 Docker 支持。

## <a name="using-docker-tools-in-visual-studio-2015"></a>在 Visual Studio 2015 中使用 Docker 工具

Visual Studio Tools for Docker 提供一致的方法来开发和验证本地 Docker 容器的 Linux Linux Docker 主机或 VM 或你直接在 Windows 上的 Windows 容器中。

如果你使用单个容器，需要开始第一件事是开启 Docker 支持在.NET Core 项目。 为此，右键单击项目文件，在图 4-25 中所示。

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

图 4-25： 打开 Visual Studio 项目的 Docker 支持

## <a name="using-docker-tools-in-visual-studio-2017"></a>在 Visual Studio 2017 中使用 Docker 工具

当你 Docker 将支持添加到服务项目解决方案中 （请参见图 4-26 日），Visual Studio 不只添加 DockerFile 文件到你的项目，它也添加服务部分在你的解决方案的 docker-compose.yml 文件 （或如果它们未创建文件存在）。 它是一种简单的方式开始编写 multicontainer 解决方案;然后可以打开 docker-compose.yml 文件并更新它们具有附加功能。

![](./media/image32.png)

图 4-26： 打开 Visual Studio 2017 项目中的 Docker 解决方案支持

此操作不只是向你的项目添加 DockerFile，它还将所需的配置的代码行添加到在解决方案级别设置全局 docker-compose.yml。

你还可以启用 Docker 支持在 Visual Studio 2017 中, 创建 ASP.NET Core 项目时在图 4-27 中所示。

![](./media/image33.png)

图 4-27： 在创建项目时开启 Docker 支持

将 Docker 支持添加到你在 Visual Studio 中的解决方案后，你还将看到在解决方案资源管理器添加的 docker-compose.yml 文件中，具有的新节点树如下图所示图 4-28。

![](./media/image34.PNG)

图 4-28: docker-compose.yml 文件现在显示在解决方案资源管理器中

你可以部署 multicontainer 应用程序运行时使用单个 docker-compose.yml 文件 docker-撰写;但是，Visual Studio 将一组添加它们，以便您可以覆盖根据环境 （而不是生产开发） 和执行的值类型 （而不是调试版本）。 此功能将更好地中后面的章节所述。

**详细信息：** 上的服务实现和使用 Visual Studio Tools for Docker 的进一步信息，请参阅以下文章：

生成、 调试、 更新和刷新本地 Docker 容器中的应用程序： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

将 ASP.NET 容器部署到远程 Docker 主机： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)


>[!div class="step-by-step"]
[上一页](docker-apps-inner-loop-workflow.md)
[下一页](set-up-windows-containers-with-powershell.md)
