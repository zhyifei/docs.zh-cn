---
title: 通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |实现现代化，使用 CI/CD 管道和 DevOps 工具在云中的应用的生命周期
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833959"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化

如今的企业需要进行创新速度很快在 marketplace 中具竞争力。 交付高质量的现代应用程序需要 DevOps 工具和流程来实现此常量的创新周期至关重要的。 使用合适的 DevOps 工具，开发人员可以简化持续部署，并更快地获取用户的手中的创新型应用程序。

尽管持续集成和部署实践制定完善，但容器引入引入了新的注意事项，尤其是在你正在使用多容器应用程序时。

Azure DevOps 服务支持持续集成和多容器应用程序部署到各种环境中完成的官方 Azure DevOps 服务部署任务：

- [在用于容器部署到 Azure Web 应用](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [将部署到 Azure 容器服务-Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

但也可以部署到[Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/)或 DC/OS 使用 Azure DevOps 服务基于脚本的任务。

若要继续推进部署灵活性，这些工具提供出色的开发到测试到生产部署容器工作负载，使用选择的开发和 CI/CD 解决方案体验。

图 4-12 显示了将部署到 Azure 容器服务中的 Kubernetes 群集的连续部署管道。

![Azure DevOps 服务持续部署管道，将部署到 Kubernetes 群集](./media/image12.png)

> **图 4 到 12 个。** Azure DevOps 服务持续部署管道，将部署到 Kubernetes 群集

>[!div class="step-by-step"]
>[上一页](modernize-your-apps-with-monitoring-and-telemetry.md)
>[下一页](migrate-to-hybrid-cloud-scenarios.md)
