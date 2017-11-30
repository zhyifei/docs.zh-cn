---
title: "决策表。 .NET 框架，用于 Docker"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |决策表，.NET 框架，用于 Docker"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4889662c4d887bebd320389e3ced6aae1c93133b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>决策表：.NET 框架，用于 Docker

下面汇总了是否使用.NET Framework 或.NET Core 和 Windows 或 Linux 容器。 请记住，对于 Linux 容器，你需要基于 Linux 的 Docker 主机 （Vm 或服务器） 和为 Windows 容器需要 Windows Server 基于 Docker 主机 （Vm 或服务器）。

有几个应用程序的功能，它们会影响你的决策。 做这些决定时，你应权衡这些功能的重要性。

> [!IMPORTANT]
> 开发计算机将运行一个 Docker 主机，Linux 或 Windows。 你想要运行和测试在一起在一个解决方案中的相关微服务将所有需要的相同容器平台上运行。

* 您的应用程序体系结构选择**在容器上的微服务**。
    - 应为.NET 实现自选*.NET 核心*。
    - 平台自选容器可以是*Linux 容器*或*Windows 容器*。
* 您的应用程序体系结构选择**整体应用程序**。
    - .NET 实现自选可以是*.NET 核心*或*.NET Framework*。
    - 如果你已选择*.NET 核心*，自选容器平台可以是*Linux 容器*或*Windows 容器*。
    - 如果你已选择*.NET Framework*，你的容器平台选择必须用*Windows 容器*。
* 你的应用程序**新容器基于开发 （"绿色的字段"）**。
    - 应为.NET 实现自选*.NET 核心*。
    - 平台自选容器可以是*Linux 容器*或*Windows 容器*。
* 你的应用程序**Windows Server 旧应用程序 （"部分的字段"） 迁移到容器**
    - .NET 实现自选是*.NET Framework*基于框架依赖项。
    - 你的容器平台选择必须用*Windows 容器*由于.NET Framework 依赖性。
* 应用程序的设计目标是**同类最佳性能和可伸缩性**。
    - 应为.NET 实现自选*.NET 核心*。
    - 平台自选容器可以是*Linux 容器*或*Windows 容器*。
* 你应用程序使用生成**ASP.NET Core**。
    - 应为.NET 实现自选*.NET 核心*。
    - 你可以使用*.NET Framework*实现中，如果你有其他框架依赖项。
    - 如果你已选择*.NET 核心*，自选容器平台可以是*Linux 容器*或*Windows 容器*。
    - 如果你已选择*.NET Framework*，你的容器平台选择必须用*Windows 容器*。
* 你应用程序使用生成**ASP.NET 4 （MVC 5，Web API 2 和 Web 窗体）**。
    - .NET 实现自选是*.NET Framework*基于框架依赖项。
    - 你的容器平台选择必须用*Windows 容器*由于.NET Framework 依赖性。
* 你的应用程序使用**SignalR 服务**。
    - 你的.NET 实现选择可以用*.NET Framework*，或*.NET 核心 2.1 （如果已发布） 或更高版本*。
    - 你的容器平台选择必须用*Windows 容器*如果.NET Framework 中选择的 SignalR 实现。
    - 如果你选择的 SignalR 实现在.NET 核心 2.1 或更高版本 （如果已发布），平台自选容器可以是 Linux 容器或 Windows 容器。  
    - 当**SignalR 服务**上运行*.NET 核心*，你可以使用*Linux 容器或 Windows 容器*。
* 你的应用程序使用**WCF、 WF、 和其他旧框架**。
    - .NET 实现自选是*.NET Framework*，或*（路线图中拥有将来的版本） 的.NET 核心*。
    - 你的容器平台选择必须用*Windows 容器*由于.NET Framework 依赖性。
* 应用程序涉及**消耗的 Azure 服务**。
    - .NET 实现自选是*.NET Framework*，或*（最终所有 Azure 服务将为.NET 核心提供客户端 Sdk） 的.NET 核心*。
    - 你的容器平台选择必须用*Windows 容器*如果你使用.NET Framework 客户端 Api。
    - 如果你使用客户端 Api 可用于*.NET 核心*，你还可以选择之间*Linux 容器和 Windows 容器*。

>[!div class="step-by-step"]
[以前](net-framework 的容器-scenarios.md) [下一步] (net-容器-os-targets.md)
