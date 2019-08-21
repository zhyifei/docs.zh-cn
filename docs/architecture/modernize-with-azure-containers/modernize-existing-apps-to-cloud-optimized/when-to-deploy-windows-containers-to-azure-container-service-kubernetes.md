---
title: 何时将 Windows 容器部署到 Azure 容器服务 (即, Kubernetes)
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |何时将 Windows 容器部署到 Azure 容器服务 (即, Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577940"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>何时将 Windows 容器部署到 Azure 容器服务 (即, Kubernetes)

Azure 容器服务专门为 Azure 优化了常用开源工具和技术的配置。 你将获得一个开放式解决方案, 该解决方案可为你的容器和应用程序配置提供可移植性。 选择大小、主机数和 orchestrator 工具。 Azure 容器服务可处理基础结构。

如果你已使用开源协调器 (如 Kubernetes、Docker Swarm 或 DC/OS), 则无需更改现有的管理实践即可将容器工作负荷迁移到云。 使用你已熟悉的应用程序管理工具, 并通过所选 orchestrator 的标准 API 终结点进行连接。

如果你使用的是 Linux Docker 容器, 但可能只是 Windows 容器的预览状态, 则所有这些协调器都是成熟环境。

例如, 在 Kubernetes 中, 对容器的支持是本机 (第一类公民), 因此, 在 Kubernetes 上使用 Windows 容器也是有效的 (在 ACS 中, 从2018年初开始)。

重要说明:适用于 Kubernetes 的 ACS (Azure 容器服务) 的发展和 "更多 PaaS" 版本为 AKS (Azure Kubernetes Service), 但是, 在第 2 2018 季度仍不支持 Windows 容器, 但不久就会受支持。

>[!div class="step-by-step"]
>[上一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[下一页](choosing-azure-compute-options-for-container-based-applications.md)
