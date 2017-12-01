---
title: ".NET 和 Docker 简介"
description: "了解 Docker 和.NET 核心"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a>.NET 和 Docker 简介

 本文提供了简介和概念与使用 Docker 上的.NET 的背景。 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker： 打包你的应用部署并运行任何位置

[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined)是使开发人员和管理员可生成一个开放平台[映像](https://docs.docker.com/glossary/?term=image)，提供，并调用松散隔离环境中运行分布式应用程序[容器](https://www.docker.com/what-container). 此方法支持开发、 QA 和生产环境之间的有效的应用程序生命周期管理。
 
[Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用[Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速生成并打包应用程序作为[Docker 映像](https://docs.docker.com/glossary/?term=image)使用编写的文件创建[Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)格式，然后是部署和运行在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)。

你可以创建你自己[分层映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)为 dockerfile 或使用现有的从[注册表](https://docs.docker.com/glossary/?term=registry)、 like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub)。

[Docker 容器、 图像和注册表之间的关系](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries)是一个重要概念时[构建和生成容器化应用程序或微服务](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/)。 此方法大大缩短了开发和部署之间的时间。

### <a name="further-reading-and-watching"></a>其他阅读材料 （和监视）

* [基于 Windows 的容器： 使用企业级控制的现代应用开发。](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Docker 概述](https://docs.docker.com/engine/docker-overview/)
* [Windows 容器上的 Dockerfile](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [编写 Dockerfile 的最佳做法](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [.NET 核心应用程序的构建 Docker 映像](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>获取.NET Docker 映像

创建和优化由 Microsoft 的官方.NET Docker 映像。 在 Docker Hub 上的 Microsoft 存储库中，公开提供。 每个存储库可以包含多个映像，具体取决于.NET 版本和操作系统版本上。 大多数映像存储库提供广泛的标记，以帮助你选择特定的 framework 版本和操作系统 （Linux 发行版或 Windows 版本）。

## <a name="scenario-based-guidance"></a>基于方案的指南

.NET 存储库的 Microsoft 的意图是具有精确的专注于存储库，它表示特定方案或工作负荷。

`microsoft/aspnetcore`映像进行优化 ASP.NET Core 上的应用程序 Docker，以便可以更快地启动容器。

.NET Core 映像 (`microsoft/dotnet`) 适用于基于.NET 核心的控制台应用。 例如，批处理、 Azure WebJobs 和其他控制台方案应使用优化的.NET Core 映像。

使用 Docker 和.NET 应用程序的最明显的水平方案适用于生产部署和托管。 事实证明生产是一个方案和其他哪些是同样有用。 这些方案并不特定于.NET 中，但应适用于大多数开发人员平台。

* **低摩擦安装**-你可以尝试.NET 而无需本地安装。 只下载使用.NET 中它的 Docker 映像。

* **在容器中进行开发**-你可以开发在一致环境中，使开发和生产环境类似 （避免如开发人员计算机上的全局状态的问题）。 Visual Studio Tools for Docker 甚至可以直接从 Visual Studio 启动容器。

* **测试容器中**-你可以在测试容器，减少由于配置不正确的环境的故障或留在原地从最后一次测试其他更改。

* **容器中生成**-你可以构建在容器中，代码避免需要正确配置为多个环境的共享的生成计算机但而将移动到"BYOC"（自带你自己的容器） 的方法。

* **在所有环境中的部署**— 您可以通过你的环境的所有部署映像。 此方法可以降低由于配置的不同，通常会更改通过外部配置 （例如，插入的环境变量） 的映像行为的故障。

[一般性指导原则](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance)的 Docker 容器开发的.NET 核心和.NET Framework 之间做出决定。

### <a name="common-docker-development-scenarios"></a>常见的 Docker 开发方案

#### <a name="net-core"></a>.NET 核心

**.NET 核心资源**

 选择适合您感兴趣的方案的.NET 核心示例。 所有的示例说明介绍如何面向 Windows、 Linux 或 macOS 主机中的 Windows 或 Linux 的 Docker 映像。

这些示例使用.NET 核心 2.0。 它们使用 Docker[多阶段生成](https://github.com/dotnet/announcements/issues/18)和[多 arch 标记](https://github.com/dotnet/announcements/issues/14)在适当的位置。

* [.NET core 映像上 DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Dockerize.NET 核心应用程序](https://docs.docker.com/engine/examples/dotnetcore/)

* 此.NET 核心 Docker 示例演示如何[在.NET 核心开发过程中使用 Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)。 示例适用于 Linux 和 Windows 容器。

* .NET 核心 Docker 演示的最佳做法模式[构建的生产.NET 核心应用程序的 Docker 映像。](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) 示例适用于 Linux 和 Windows 容器。

* 这[.NET 核心 Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained)演示生成的 Docker 映像的最佳做法模式[自包含的.NET Core 应用](https://docs.microsoft.com/dotnet/core/deploying/)。 用于最小的生产容器，而无需受益于[共享容器之间的基础映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)。 但是，无法共享较低的 Docker 层。

#### <a name="arm32--raspberry-pi"></a>ARM32 / Raspberry Pi

* [.NET 核心运行时 ARM32 生成公告](https://github.com/dotnet/announcements/issues/29)

* [ARM32 / Raspberry Pi.NET Core 映像上 DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [ARM32 / 树莓 Pi.NET 核心 Docker 示例 GitHub 上](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [.NET framework 映像上 DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/)此存储库包含演示各种.NET Framework Docker 配置的示例。 作为你自己的 Docker 映像的基础，可使用这些映像。

**.NET framework 4.7**

[ [Dotnet-framework: 4.7 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7)演示基本"你好 world"用法的[.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47)。 它演示如何生成并部署应用程序依赖于[.NET Framework 4.7 docker 映像](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile)。

**.NET framework 4.6.2**

[Dotnet-framework: 4.6.2 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2)演示基本"你好 world"用法的[.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462)。 它演示如何生成并部署应用程序依赖于[.NET Framework 4.6.2 docker 映像](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2)。

**.NET framework 3.5**

 [Dotnet-framework: 3.5 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5)演示基本"你好 world"用法的[.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5)。 它演示如何生成并部署依赖于在 Docker 中的.NET Framework 3.5 的项目。

#### <a name="aspnet-core"></a>ASP.NET Core

* [此 ASP.NET 核心 Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)演示针对适用于生产应用的 ASP.NET Core 构建 Docker 映像的最佳做法模式。 示例适用于 Linux 和 Windows 容器。

* [DockerHub 上的 ASP.NET Core 映像](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [在 GitHub 上的 ASP.NET Core 映像](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>ASP.NET Framework 

* [DockerHub 上的 ASP.NET 框架映像](https://hub.docker.com/r/microsoft/aspnet/)

* [在.NET Framework 4.6.2 示例上的 ASP.NET Web 窗体应用程序](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [DockerHub 上的 Windows Communication Framework (WCF) 映像](https://hub.docker.com/r/microsoft/wcf/)

* [在 GitHub 上的 Windows Communication Framework (WCF) 映像](https://github.com/microsoft/iis-docker)

* [使用.NET Full Framework 4.6.2 Windows Communication Framework (WCF) Docker 示例](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet 信息服务器 (IIS)

* [DockerHub 上的 Internet 信息服务器 (IIS) 映像](https://hub.docker.com/r/microsoft/iis/)

* [在 GitHub 上的 Internet 信息服务器 (IIS) 映像](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>与其他 Microsoft 堆栈容器映像进行交互

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [使用 Docker 快速入门中运行 Microsoft SQL Server 并执行自 2017 年 Linux 容器映像](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [DockerHub 上的 Linux 映像的 Microsoft SQL Server](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [DockerHub 上的 Microsoft SQL Server 的 Windows 容器映像](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Microsoft SQL Server Express Edition DockerHub 上的 Windows 容器映像](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Microsoft SQL Server Developer Edition DockerHub 上的 Windows 容器映像](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Visual Studio Team Services (VSTS) 代理

* [DockerHub 上的 visual Studio Team Services (VSTS) 代理映像](https://hub.docker.com/r/microsoft/vsts-agent/)

* [在 GitHub 上的 visual Studio Team Services (VSTS) 代理映像](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Operations Management Suite (OMS) Linux 代理

* [Operations Management Suite (OMS) Linux 代理概述](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [DockerHub 上的 operations Management Suite (OMS) 映像](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [在 GitHub 上的 operations Management Suite (OMS) 映像](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Microsoft Azure 命令行界面 (CLI)

* [DockerHub 上的 Microsoft Azure 命令行界面 (CLI) 映像](Docker image for Microsoft Azure Command Line Interface) 

* [在 GitHub 上的 Microsoft Azure 命令行界面 (CLI) 映像](https://github.com/Microsoft/OMS-docker)

> [!Note]
> 如果你没有 Azure 订阅，[现在注册](https://azure.microsoft.com/free/?b=16.48)免费的 30 天帐户和 get 200 美元的 Azure 信用额度来试用 Azure 服务的任意组合。
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Microsoft Azure Cosmos DB 模拟器 （仅适用于 Windows 容器）

* [DockerHub 上的 Microsoft Azure Cosmos DB 仿真程序映像](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [使用 Azure Cosmos DB 仿真程序用于本地开发和测试](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>浏览丰富的 Docker 开发生态系统

现在，你已了解有关 Docker 平台和不同的 Docker 映像下, 一步是浏览丰富 Docker 生态系统。 以下链接将显示 Microsoft 工具对容器开发的补充。

* [将.NET 与 Docker 一起使用](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [设计和开发多容器和基于微服务的.NET 应用程序](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [Visual Studio 代码 Docker 扩展](https://code.visualstudio.com/docs/languages/dockerfile) 
* [了解如何使用 Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/) 
* [Service Fabric 获取启动示例](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [Windows 容器的优点](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [使用 Visual Studio Docker 工具](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [部署到 Azure 容器实例中 Azure 容器注册表的 Docker 映像](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [使用 Visual Studio 代码进行调试](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [获取之手使用 Visual Studio Mac、 容器和无服务器代码在云中](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [开始使用 Docker 和 Visual Studio Mac 实验室](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a>后续步骤

* [了解 Docker 使用.NET Core 的基础知识](../docker/docker-basics-dotnet-core.md)
* [构建.NET 核心 Docker 映像](../docker/building-net-docker-images)