---
title: 决策表。 用于 Docker 的 .NET Framework
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 决策表，用于 Docker 的 .NET Framework
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 0e384fabca88d8ad6f93ae626140fb3d5dcaf971
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589316"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>决策表：用于 Docker 的 .NET Framework

下面汇总了是使用 .NET Framework 还是 .NET Core、Windows 还是 Linux 容器。 请记住，对于 Linux 容器，你需要基于 Linux 的 Docker 主机（VM 或服务器）；对于 Windows 容器，你需要基于 Windows Server 的 Docker 主机（VM 或服务器）。

有几个应用程序的功能会影响你的决定。 作决定时，应权衡这些功能的重要性。

> [!IMPORTANT]
> 开发计算机将运行一个 Docker 主机，Linux 或 Windows 均可。 想在一个解决方案中一起运行和测试的相关微服务都需要在同一容器平台上运行。

* 应用程序体系结构要选择容器上的微服务。
    - .NET 实现应选择 .NET Core。
    - 容器平台可以选择 Linux 容器或 Windows 容器。
* 应用程序体系结构要选择整体式应用程序。
    - .NET 实现可以选择 .NET Core 或 .NET Framework。
    - 如果选择 .NET Core，容器平台可以选择 Linux 容器或 Windows 容器。
    - 如果选择的是 .NET Framework，容器平台必须选择 Windows 容器。
* 应用程序是基于容器的新开发（“绿色字段”）。
    - .NET 实现应选择 .NET Core。
    - 容器平台可以选择 Linux 容器或 Windows 容器。
* 应用程序是到容器的 Windows Server 旧应用程序（“棕色字段”）迁移
    - .NET 实现要选择基于框架依赖关系的 .NET Framework。
    - 因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。
* 应用程序的设计目标是同类最佳的性能和可伸缩性。
    - .NET 实现应选择 .NET Core。
    - 容器平台可以选择 Linux 容器或 Windows 容器。
* 使用 ASP.NET Core 生成应用程序。
    - .NET 实现应选择 .NET Core。
    - 如果有其他框架依赖关系，可以使用 .NET Framework 实现。
    - 如果选择 .NET Core，容器平台可以选择 Linux 容器或 Windows 容器。
    - 如果选择的是 .NET Framework，容器平台必须选择 Windows 容器。
* 使用 ASP.NET 4（MVC 5、Web API 2 和 Web Forms）生成了应用程序。
    - .NET 实现要选择基于框架依赖关系的 .NET Framework。
    - 因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。
* 应用程序使用 SignalR 服务。
    - .NET 实现可以选择 .NET Framework 或者 .NET Core 2.1（如发布）或更高版本。
    - 如果选择 .NET Framework 中的 SignalR 实现，则容器平台必须选择 Windows 容器。
    - 如果选择 .NET Core 2.1 或更高版本（如发布）中的 SignalR 实现，则容器平台可以选择 Linux 容器或 Windows 容器。  
    - 当 SignalR 服务在 .NET Core 上运行时，可以使用 Linux 容器或 Windows 容器。
* 应用程序使用 WCF、WF 和其他旧框架。
    - .NET 实现可以选择 .NET Framework 或 .NET Core（未来版本的路线图中）。
    - 因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。
* 应用程序涉及 Azure 服务的消耗。
    - .NET 实现可以选择 .NET Framework 或 .NET Core（最终所有 Azure 服务都将为 .NET Core 提供客户端 SDK）。
    - 如果使用 .NET Framework 客户端 API，容器平台必须选择 Windows 容器。
    - 如果使用适用于 .NET Core 的客户端 API，还可选择 Linux 容器或 Windows 容器。

>[!div class="step-by-step"]
[上一页] (net-framework-container-scenarios.md) [下一页] (net-container-os-targets.md)
