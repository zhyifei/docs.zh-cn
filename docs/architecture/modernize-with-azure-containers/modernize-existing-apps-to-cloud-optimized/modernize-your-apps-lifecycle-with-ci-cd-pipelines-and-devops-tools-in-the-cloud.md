---
title: 通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |在云中通过 CI/CD 管道和 DevOps 工具现代化应用程序的生命周期
ms.date: 04/30/2018
ms.openlocfilehash: 62b6c541780ed3bf82c55e576fa485f811b55b17
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374143"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化

如今的企业需要快速创新，才能在 marketplace 中获得竞争力。 交付高质量的新式应用程序需要 DevOps 工具和过程，这些工具和过程对于实现这一不断创新的循环至关重要。 借助适当的 DevOps 工具，开发人员可以简化持续部署，并更快地让用户获得创新的应用程序。

尽管持续集成和部署做法已建立良好的发展，但引入容器也会引入新的注意事项，尤其是在使用多容器应用程序时。

Azure DevOps Services 通过官方 Azure DevOps Services 部署任务支持将多容器应用程序持续集成和部署到各种环境：

- [部署到 Azure 用于容器的 Web 应用](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [部署到 Azure 容器服务– Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

但你还可以使用基于 Azure DevOps Services 脚本的任务部署到[Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/)或 DC/OS。

为了继续促进部署灵活性，这些工具为容器工作负载提供了完美的开发到生产部署体验，同时提供了一系列开发和 CI/CD 解决方案。

图4-12 显示了部署到 Azure 容器服务中的 Kubernetes 群集的持续部署管道。

![Azure DevOps Services 连续部署管道，部署到 Kubernetes 群集](./media/image12.png)

**图4-12。** Azure DevOps Services 连续部署管道，部署到 Kubernetes 群集

>[!div class="step-by-step"]
>[上一页](modernize-your-apps-with-monitoring-and-telemetry.md)
>[下一页](migrate-to-hybrid-cloud-scenarios.md)
