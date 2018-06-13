---
title: 何时将 Windows 容器部署到 Azure 容器服务 (即，Kubernetes)
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |何时将 Windows 容器部署到 Azure 容器服务 (即，Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958167"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>何时将 Windows 容器部署到 Azure 容器服务 (即，Kubernetes)

Azure 容器服务优化了针对 Azure 的受欢迎的开源工具和技术配置。 获取一个打开的解决方案，它提供可移植性对于你的容器和应用程序配置。 你选择的大小、 的主机，数量和 orchestrator 工具。 Azure 容器服务为你处理基础结构。

如果你已使用开放源代码 orchestrators Kubernetes、 Docker Swarm，或 DC/OS 等，不需要更改您现有的管理做法将容器工作负荷移到云。 使用你已熟悉的应用程序管理工具，并通过标准的 API 终结点连接的所选 orchestrator。

如果你使用 Linux Docker 容器，但可能仅处于预览状态，为 Windows 容器，则所有这些 orchestrators 是成熟的环境。

例如，在 Kubernetes，支持容器为本机 （第一类公民），因此在 Kubernetes 上使用 Windows 容器也很有效 （在 ACS 中截至早期 2018年的预览版）。

重要说明： 系统要求和"详细 PaaS"Kubernetes ACS （Azure 容器服务） 的版本是 AKS （Azure Kubernetes 服务），但是，Windows 容器仍不支持从季 2 季 2018年开始，但很快将支持。

>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-to-service-fabric.md)
[下一页](choosing-azure-compute-options-for-container-based-applications.md)
