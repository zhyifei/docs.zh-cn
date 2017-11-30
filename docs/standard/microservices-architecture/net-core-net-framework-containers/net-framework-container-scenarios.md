---
title: "何时选择 Docker 容器中的.NET Framework"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |何时选择 Docker 容器中的.NET Framework"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>何时选择 Docker 容器中的.NET Framework

虽然.NET 核心提供显著的好处，为新的应用程序和应用程序模式，.NET Framework 将持续成为适合于许多现有方案。

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>迁移现有应用程序直接到 Windows Server 容器

你可能想要使用 Docker 容器只是为了简化部署，即使你不在创建微服务。 例如，可能是你想要提高你 DevOps 工作流使用 Docker，容器可以为你提供更好地隔离的测试环境，并还可以消除引起缺少的依赖关系，你将移动到生产环境时的部署问题。 在类似这样的情况下，即使你要部署的整体应用程序，最好为当前.NET Framework 应用程序中使用 Docker 和 Windows 容器。

在大多数情况下，对于这种情况下，将不需要迁移到.NET 核心; 的现有应用程序你可以使用包括传统的.NET Framework 的 Docker 容器。 但是，建议的方法是使用.NET 核心扩展现有的应用程序，例如，在 ASP.NET 核心中写入新的服务。

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>为.NET 核心使用第三方.NET 库或不可用的 NuGet 包

第三方库快速开始采用[.NET 标准](https://docs.microsoft.com/dotnet/standard/net-standard)，这可使在各种.NET 版本，包括.NET 核心之间共享的代码。 .NET 标准库 2.0 和更高版本的 API 图面跨不同的框架的兼容性变得明显更大，.NET 核心 2.0 中应用程序还可以直接引用现有的.NET Framework 库 (请参阅[compat填充码](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work))。

但是，即使使用由于.NET 标准 2.0 和.NET 核心 2.0 该异常前进，可能有情况下，其中某些 NuGet 包需要 Windows 运行，但可能不支持.NET 核心。 如果这些包都是关键应用程序，你将需要在 Windows 容器上使用.NET Framework。

## <a name="usingnet-technologies-not-available-for-net-core"></a>不可用于.NET 核心的 Using.NET 技术 

某些.NET Framework 技术将不可用.NET 核心 （撰写本文时版本 2.0） 的当前版本中。 其中一些可在更高版本的.NET Core 版本 (.NET 核心 2.x)，但其他不适用于新的应用程序模式针对.NET Core 和可能永远不能使用。

以下列表显示在.NET 核心 2.0 中不可用的技术的大多数：

-   ASP.NET Web 窗体。 仅在.NET Framework 上提供了此技术。 目前没有将 ASP.NET Web 窗体引入 .NET Core 的计划。

-   WCF 服务。 即使[WCF 客户端库](https://github.com/dotnet/wcf)可使用从.NET 核心的 WCF 服务。 截至中旬 2017 WCF 服务器实现仅在.NET Framework 上可用。 这种情况下可视为针对将来版本的.NET 核心。

-   与工作流相关的服务。 Windows Workflow Foundation (WF)、 工作流服务 （WCF + WF 中单个服务） 和 WCF 数据服务 （以前称为 ADO.NET Data Services） 才在.NET Framework 上可用。 目前没有计划，以使它们到.NET 核心。

除了技术之外列入官方[.NET 核心路线图](https://github.com/aspnet/Home/wiki/Roadmap)，其他功能可能移植到.NET 核心。 有关完整列表，查看的项标记为[端口核心](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core)CoreFX GitHub 站点上。 请注意，此列表不表示从 Microsoft 的承诺，以使这些组件进入.NET 核心 — 项只需捕获来自社区的请求。 如果您关心任何上面列出的组件，请考虑参与 GitHub 上的讨论，以便可以听到您的声音。 如果认为丢失了某些内容，请[在 CoreFX 存储库中提出新的问题](https://github.com/dotnet/corefx/issues/new)。

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>使用平台或不支持.NET 核心的 API

某些 Microsoft 或第三方平台不支持.NET 核心。 例如，某些 Azure 服务提供尚不可用在.NET Core 上使用的 SDK。 这是临时的因为所有 Azure 服务最终将使用.NET 核心。 例如， [Azure DocumentDB SDK for.NET 核心](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1)发布为预览在 2016 年 11 月 16 日，但它现在是稳定的版本为正式版 (GA)。

在此期间，如果任何平台或在 Azure 中的服务仍不支持.NET 核心使用其客户端 API，你可以在.NET Framework 上使用等效的 REST API 从 Azure 服务或客户端 SDK。

### <a name="additional-resources"></a>其他资源

-   **.NET 核心指南**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)

-   **从.NET Framework 移植到.NET 核心**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)

-   **.NET framework 在 Docker 指南上的**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)

-   **.NET 组件概述**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)




>[!div class="step-by-step"]
[以前](net-核心-容器-scenarios.md) [下一步] (容器-framework-选择-factors.md)
