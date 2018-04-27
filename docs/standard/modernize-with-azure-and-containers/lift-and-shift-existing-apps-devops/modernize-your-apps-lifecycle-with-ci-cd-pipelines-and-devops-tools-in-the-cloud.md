---
title: 更新使用 CI/CD 管道和 DevOps 工具在云中的应用程序的生命周期
description: 为容器化的.NET 应用程序的.NET 微服务体系结构 |更新使用 CI/CD 管道和 DevOps 工具在云中的应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 56dbd4a867e0f47d0f7e681d924584629d763f87
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>更新使用 CI/CD 管道和 DevOps 工具在云中的应用程序的生命周期

如今的企业需要在较快的速度要应用商店中竞争对手创新。 提供高质量，现代应用程序要求的都是关键实现创新此常量周期 DevOps 工具和过程。 使用适当的 DevOps 工具，开发人员可以简化连续部署和更快速地获取的用户到手中的创新应用程序。

虽然连续集成和部署实践成熟，但容器简介引入了新的注意事项，尤其是在你正在使用多容器应用程序时。

Visual Studio Team Services 支持持续集成和部署多容器应用程序到各种环境中完成的正式的 Team Services 部署任务：

-   [将部署到独立的 Docker 主机 VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) （Linux 或 Windows Server 2016 或更高版本）

-   [将部署到 Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [将部署到 Azure 容器服务 – Kubernetes](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

但你也可以部署到[Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/)或 DC/OS 使用 Team Services 基于脚本的任务。

若要继续推进部署灵活性，这些工具提供出色开发到测试到生产部署遇到对于容器的工作负荷，通过选择的开发和 CI/CD 解决方案。

图 4-12 显示将部署到 Azure 容器服务中的实现 Kubernetes 群集的连续部署管道。

![Visual Studio Team Services 连续部署管道，到 Kubernetes 群集部署](./media/image12.png)

> **图 4-12。** Visual Studio Team Services 连续部署管道，到 Kubernetes 群集部署

>[!div class="step-by-step"]
[上一页](modernize-your-apps-with-monitoring-and-telemetry.md)
[下一页](migrate-to-hybrid-cloud-scenarios.md)
