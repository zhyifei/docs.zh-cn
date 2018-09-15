---
title: 使用 Microsoft 工具的 Docker 应用程序 DevOps 工作流
description: 使用 Microsoft 平台的容器化 Docker 应用程序生命周期和使用 Microsoft 工具的 ToolsDevOps 工作流
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d313cb8ff6762eba6534ca20b214063315a456f0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45639180"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>使用 Microsoft 工具的 Docker 应用程序 DevOps 工作流

Microsoft Visual Studio、 Azure DevOps 服务、 Team Foundation Server 和 Application Insights 为开发和为你的团队提供的工具来管理项目和快速生成、 测试和部署的 IT 运营提供综合的生态系统容器化应用程序。

使用 Visual Studio 和 Azure DevOps 服务在云中，以及 Team Foundation Server 的本地开发团队还可以高效地构建、 测试和发布面向任何平台 （Windows 或 Linux） 的容器化应用程序。

Microsoft 工具可以自动完成的容器化应用程序的具体实现管道-Docker、.NET Core 或与其他平台的任意组合 — 从全局生成和持续集成 (CI) 和使用 Azure DevOps 服务或团队的测试Foundation Server，到持续部署 (CD) 到 Docker 环境 （开发、 过渡、 生产），并向开发团队通过 Application Insights 服务的分析信息传输。 每个代码提交都能启动生成 (CI) 过程并自动将服务部署到特定的容器化环境 (CD)。

开发者和测试者可以使用 Microsoft Azure 中的模板快速轻松地配置生产环境，如基于 Docker 的开发和测试环境。

容器化应用程序开发的复杂度根据业务复杂度和可伸缩性需要逐步增加。 一个很好的示例就是基于微服务体系结构的应用程序。 要在此类环境中取得成功，你的项目必须在整个生命周期（而不仅是在生成和部署阶段）实现自动化，同时还必须管理版本并收集遥测数据。 Azure DevOps 服务和 Azure 提供了以下功能：

-   Azure DevOps Services/Team Foundation Server 源代码管理 （基于 Git 或 Team Foundation 版本控制），敏捷规划 （Agile、 Scrum 和 CMMI 支持），CI、 发布管理和敏捷团队的其他工具。

-   Azure DevOps Services/Team Foundation Server 包括第一个和第三方扩展与您轻松地可以构造 CI、 生成、 测试、 交付和发布管理管道微服务的一个功能强大且不断增长的生态的系统。

-   运行自动的测试作为生成管道中 Azure DevOps 服务的一部分。

-   Azure DevOps 服务可以增强 DevOps 生命周期与传递到多个环境，而不仅仅是对于生产环境，还适用于测试，包括 A / B 试验[canary 发布](https://martinfowler.com/bliki/CanaryRelease.html)，依次类推。

-   组织可以使用 Azure 资源管理器和熟悉的工具，轻松从 Azure 容器注册表中存储的专用映像配置 Docker 容器以及 Azure 组件（数据、PaaS 等）的任何依赖项。


>[!div class="step-by-step"]
[上一页](../design-develop-containerized-apps/set-up-windows-containers-with-powershell.md)
[下一页](docker-application-outer-loop-devops-workflow.md)
