---
title: "正式.NET Docker 映像"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |正式.NET Docker 映像"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a>正式.NET Docker 映像

官方.NET Docker 映像是创建和优化的 Microsoft 的 Docker 映像。 它们中公开可用的 Microsoft 存储库上[Docker Hub](https://hub.docker.com/u/microsoft/)。 每个存储库可以包含多个映像，具体取决于.NET 版本，并根据操作系统和版本 （Linux Debian、 Linux Alpine、 Windows Nano Server、 Windows Server Core 等）。

.NET 存储库的 Microsoft 的愿景是让精细的专注于存储库，其中存储库表示特定方案或工作负荷。 例如， [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)上 Docker，使用 ASP.NET Core，因为这些 ASP.NET Core 映像提供额外的优化是容器可以更快地启动时，应使用映像。

另一方面，.NET 核心映像 (microsoft/dotnet) 用于基于.NET 核心的控制台应用。 例如，批处理、 Azure WebJobs 和其他控制台方案应使用.NET 核心。 这些映像不包括 ASP.NET Core 堆栈，从而导致较小的容器映像。

大多数映像存储库提供大量标记，来帮助你选择不只是特定的框架版本中，而且还可以选择的操作系统 （Linux 发行版或 Windows 版本）。

由 Microsoft 提供的正式.NET Docker 映像的详细信息，请参阅[.NET Docker 映像摘要](https://aka.ms/dotnetdockerimages)。

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>用于与生产开发的.NET 核心和 Docker 映像优化

当为开发人员构建 Docker 映像，Microsoft 将侧重于以下主要方案：

-   使用到的图像*开发*和生成.NET Core 应用。

-   使用到的图像*运行*.NET Core 应用。

为什么多个映像？ 当开发、 构建和运行容器化应用程序时，你通常具有不同的优先级别。 通过适用于这些单独的任务提供不同的映像，Microsoft 有助于优化的开发、 构建和部署应用程序的单独进程。

### <a name="during-development-and-build"></a>在开发和生成过程

在开发期间，重要的一点是速度可循环更改和调试所做的更改的能力。 图像的大小不是对代码进行更改并快速查看的更改的功能与同等重要的。 某些工具和"生成代理容器"，使用开发 ASP.NET Core 映像 （microsoft/aspnetcore-生成） 在开发过程和生成流程。 构建在 Docker 容器内时, 的重要方面是为了编译你的应用程序所需要的元素。 这包括编译器和任何其他.NET 依赖关系，以及 npm，如 web 开发依赖项的 Gulp，和 Bower。

此类型的生成映像为什么很重要？ 你无需向生产部署此映像。 相反，它是用于放置的内容生成到生产映像的映像。 在持续集成 (CI) 环境或生成环境中，将使用此映像。 例如，而不是直接在生成代理上手动安装所有应用程序依赖关系托管 (例如，一个 VM)，生成代理会在生成应用程序所需的所有依赖项的情况下实例化.NET Core 生成映像。 生成代理只需要了解如何运行此 Docker 映像即可。 这简化了 CI 环境，并使其更可预测。

### <a name="in-production"></a>在生产环境中

在生产中重要的是如何快速你可以部署和启动你的生产.NET Core 映像所基于的容器。 因此，仅运行时映像基于[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)很小，以便它可以快速通过网络传输从 Docker 注册表到 Docker 主机。 内容已准备好运行，启用从启动到处理结果容器时间最短。 在 Docker 模型中，没有编译 C 中无需\#代码，因为存在正在运行 dotnet 生成或 dotnet 发布时时使用生成容器。

在此优化的映像您放入仅的二进制文件和运行应用程序所需的其他内容。 例如，由 dotnet 创建的内容发布包含已编译的.NET 二进制文件、 映像、.js 和.css 文件。 随着时间推移，你将看到包含 pre jitted 包的映像。

虽然有多个版本的.NET Core 和 ASP.NET Core 映像，但它们都共享一个或多个层，包括基本层。 因此，存储映像所需的磁盘空间量是小;它仅包含自定义映像和其基础的映像之间的增量。 结果是，它是快速从您的注册表中提取映像。

当你浏览在 Docker Hub.NET 映像存储库时，您会发现多个映像版本分类或标记与标记。 这些标记可帮助决定要使用，根据需要类似于下表中的版本哪一种：

-   microsoft /**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   microsoft /**aspnetcore-生成： 2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[以前](net-容器-os-targets.md) [下一步] (.../architect-microservice-container-applications/index.md)
