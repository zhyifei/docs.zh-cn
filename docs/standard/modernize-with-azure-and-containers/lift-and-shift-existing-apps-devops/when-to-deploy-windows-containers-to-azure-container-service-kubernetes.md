---
title: "何时将 Windows 容器部署到 Azure 容器服务 (即，Kubernetes)"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |何时将 Windows 容器部署到 Azure 容器服务 (即，Kubernetes)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: f5ba7aa2cf14e7ca9f3a1f3eb12bbe236dca7e97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>何时将 Windows 容器部署到 Azure 容器服务 (即，Kubernetes)

Azure 容器服务优化了针对 Azure 的受欢迎的开源工具和技术配置。 获取一个打开的解决方案，它提供可移植性对于你的容器和应用程序配置。 你选择的大小、 的主机，数量和 orchestrator 工具。 Azure 容器服务为你处理基础结构。

如果你已使用开放源代码 orchestrators Kubernetes、 Docker Swarm，或 DC/OS 等，不需要更改您现有的管理做法将容器工作负荷移到云。 使用你已经熟悉，并通过标准的 API 终结点连接的所选 orchestrator 的应用程序管理工具。

如果你在使用 Linux Docker 容器，但它们还支持 Windows 容器如 2017 （有些是更早版本，有些时间更近，根据 orchestrator），则所有这些 orchestrators 是成熟的环境。

例如，在 Kubernetes，支持容器为本机 （第一类公民），因此在 Kubernetes 上使用 Windows 容器也是非常有效且可靠 （直到预览中尽早在 2017 年）。

>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-to-service-fabric.md)
[下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
