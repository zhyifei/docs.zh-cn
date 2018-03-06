---
title: "使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序"
description: "使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序 | 简介"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1140a18aba685f3415d7c599d1b76648bf9924e7
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序

![封面图像](./media/cover.jpg)


相比传统 .NET 开发，.NET Core 和 ASP.NET Core 具有一系列优势。 如果以下所有方面或一些方面对于你的应用程序成功至关重要，应将 .NET Core 用于服务器应用程序：

-   跨平台支持

-   微服务的使用

-   Docker 容器的使用

-   高性能和可伸缩性要求

-   在同一服务器上通过应用程序对 .NET 版本进行并行版本控制

传统 .NET 应用程序虽然支持以上要求，但是 ASP.NET Core 和 .NET Core 已经过优化，可为以上方案提供完善的支持。

越来越多的组织选择使用 Microsoft Azure 等服务，在云中托管 web 应用程序。 如果以下方面对你的应用程序或组织至关重要，应该考虑在云中托管应用程序：

-   减少对数据中心的成本投入（硬件、软件、空间、实用工具等）

-   灵活的定价（基于使用情况付费，无需为空闲容量付费）

-   高可靠性

-   改善应用移动性；可轻松更改部署应用的位置和方式

-   灵活的容量；基于实际需要增加或减少

使用 Microsoft Azure 中托管的 ASP.NET Core 生成 web 应用程序，与传统替代方法相比，这能提供许多竞争优势。 ASP.NET Core 针对新式 web 应用程序开发做法和云托管方案进行了优化。 本指南介绍如何构建 ASP.NET Core 应用程序，充分利用这些功能。

## <a name="purpose"></a>目标

本指南提供了使用 ASP.NET Core 和 Azure 构建单片 web 应用程序的端到端指导。

本指南是对“使用 .NET 构建和开发容器化和基于微服务的应用程序”的补充，偏重于 Docker、微服务和托管企业应用程序的容器部署。

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a>在 .NET 中构建和开发基于微服务的容器化应用
> - 电子书  
> <http://aka.ms/MicroservicesEbook>
> - 示例应用程序  
> <http://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>本指南的目标读者

本指南的受众主要是对使用云中的 Microsoft 技术和服务生成新式 web 应用程序感兴趣的开发者、开发潜在顾客和架构师。

次要受众是技术决策制定者，他们已经熟悉 ASP.NET 和/或 Azure，并想要了解是否需要为新项目或现有项目升级到 ASP.NET Core。

## <a name="how-you-can-use-this-guide"></a>如何使用本指南

本指南已精简为较小的文档，侧重介绍如何使用新式 .NET 技术和 Windows Azure 生成 web 应用程序。 可通读本指南，了解有关此类应用程序及其技术注意事项的基本信息。 本指南及其示例应用程序还可作为操作起点或参考。 可将相关示例应用程序作为你自己的应用程序的模板，或者了解如何组织应用程序的组件部件。 在对自己的应用程序进行选择权衡时，请参考指南的原则、体系结构的范围以及技术选项和决策注意事项。

请将本指南转发到团队中，这有助于确保对这些注意事项和机会的共同理解。 确保每个人使用共同的术语和基础原则工作，这有助于构建模式和做法的一致应用。

## <a name="references"></a>参考资料
- **为服务器应用选择 .NET Core 或 .NET Framework**  
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
[下一个] (modern-web-applications-characteristics.md)
