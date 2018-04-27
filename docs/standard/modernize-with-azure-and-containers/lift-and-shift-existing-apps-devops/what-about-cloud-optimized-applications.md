---
title: 云优化应用程序如何呢？
description: 为容器化的.NET 应用程序的.NET 微服务体系结构 |云优化应用程序如何呢？
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 63eb80dc43e174f4c803f772f09f6e72d8c8e7c2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="what-about-cloud-optimized-applications"></a>云优化应用程序如何呢？

尽管云优化和[云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)应用程序不是主要关心的本指南中，是很有帮助，以便了解此现代化成熟度，从而将它从云 DevOps 就绪区分开来。

图 4-3 将置于应用程序现代化成熟度云优化应用：

![定位云优化应用程序](./media/image3.png)

> **图 4-3。** 定位云优化应用程序

云优化现代化成熟度通常需要新的开发投资。 移到云优化级别通常根据业务需求来提升应用程序尽可能多地以降低成本并提高了灵活性，并争取优点。 最大程度地利用云 PaaS 可以实现这些目标。 这意味着不仅像 DBaaS、 CaaS 和存储作为一项服务 (STaaS)，但还通过将你自己的应用程序和服务迁移到 PaaS 计算平台 Azure App Service，如使用 PaaS 服务或使用 orchestrators。

这种类型的现代化通常需要重构或编写新代码，非常适合云 PaaS 平台 （如对 Azure App Service 部署时）。 它甚至可能需要构建专为云环境中，尤其是如果你正在将它们移动到基于微服务的云本机应用程序模型。 这是一个区分因素与云 DevOps 就绪，这需要任何重新构建和任何新代码相比的密钥。

在某些更高级的情况下，可能会创建[云本机](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)应用程序基于微服务体系结构，这可以借助灵活性不断变化，并且扩展到将会很难实现在整体体系结构中的限制部署到本地环境。

图 4-4 显示使用云优化模型时可以部署的应用程序的类型。 你有两个基本选项现代 web 应用程序和云本机应用程序。

> ![在云优化级别的应用类型](./media/image4.png)
>
> **图 4-4。** 在云优化级别的应用类型

可以通过添加其他服务，如人工智能 (AI)、 机器学习 (ML) 和 IoT 扩展基本现代应用 web 程序和云本机应用。 你可能使用这些服务的任何扩展任何可能的云优化方法。

在云优化级别的应用程序中的重要差别在于在应用程序体系结构。 [云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)应用程序是，根据定义，基于微服务的应用。 云本机应用需要特殊的体系结构、 技术和平台，相比整体 web 应用程序或传统的 N 层应用程序。

创建新应用程序不使用微服务也有意义。 有许多新的和仍现代方案在其中一种微服务基于方法可能会超出你的需求。 在某些情况下，你可能只是想要创建一个更简单的整体 web 应用程序，或将粗粒度的服务添加到 N 层应用程序。 在这些情况下，你仍可以完全使用云的类似 Azure App Service 所提供的 PaaS 功能。 你仍可以限制到减少维护工作。

此外，因为开发新代码在云优化方案中 （为完整的应用程序或部分子系统），当您创建新的代码，你应使用较新版本的.NET ([.NET 核心](../../../core/index.md)和[ASP.NET Core](/aspnet/core/)，尤其是)。 这是如果因为.NET 核心是一个框架，精益和快速创建微服务和容器尤其如此。 你会获得小的内存需求量和在容器中，快速开始，你的应用程序将高性能。 此方法十分适合与需求微服务和容器，并获得跨平台框架能够在 Linux、 Windows Server 和 Mac (Mac 开发环境) 上运行同一应用程序的优点。

## <a name="cloud-native-applications-with-cloud-optimized-applications"></a>与云优化应用程序的云本机应用程序

[云本机](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)为大型和任务关键型应用程序的更高级或成熟状态。 云本机应用程序通常需要体系结构和设计而不是从头创建的 modernizing 现有应用程序。 云本机应用程序和更简单云优化 web 应用部署到 PaaS 的主要区别是用于在云本机方法中的微服务体系结构的建议。 云优化应用也可以是单一的 web 应用或 N 层应用程序部署到云等 Azure App Service 的 PaaS 服务。

[十二个因素应用](https://12factor.net/)（密切相关到微服务方法的模式的集合） 也被视为一项要求[云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)应用程序体系结构。

[云本机计算 Foundation (CNCF)](https://www.cncf.io/)是云本机原则主提升程序。 Microsoft 是[CNCF 成员](https://azure.microsoft.com/blog/announcing-cncf/)。

有关示例定义和特征的云本机应用程序的详细信息，请参阅 Gartner 文章[如何构建和设计云本机应用程序](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)。 有关如何实现云本机应用程序从 Microsoft 的具体指引，请参阅[.NET 微服务： 为容器化的.NET 应用程序的体系结构](https://aka.ms/microservicesebook)。

要考虑是否你迁移到完整的应用程序，最重要的因素[云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)模型是，您必须重新构建到基于微服务的体系结构。 这清楚地由于涉及的大型重构过程需要大量的开发。 选择此选项，通常是任务关键型应用程序需要更高级别的可伸缩性和长期的灵活性。 但是，你可以开始在移至云本机通过添加只需少量的新方案的微服务并最终重构完全作为微服务应用程序。 这是递增的方法是在某些情况下的最佳选项。

## <a name="what-about-microservices"></a>有关微服务的新增功能？ 

在为你的组织考虑云本机应用程序，了解微服务以及它们如何工作非常重要。

微服务体系结构是可用于从零开始或改进现有应用程序创建的应用程序的高级的方法 （在本地或云 DevOps 准备就绪，可以应用程序） 向云本机应用程序。 你可以通过将几个微服务添加到现有应用程序若要了解有关新的微服务范例。 但很显然，你需要的架构师和代码，尤其是对于这种体系结构的方法。

但是，微服务并不是强制的任何新的或现代应用程序。 微服务不是"幻项目符号，"，并且它们不创建每个应用程序的单一的最佳方法。 如何以及何时使用微服务取决于生成所需的应用程序的类型。

微服务体系结构已变得分布式和大型或复杂的任务关键型应用程序基于自治服务形式的多个独立子系统的首选的方法。 在基于微服务的体系结构，应用程序生成为一个服务可以是独立开发、 测试、 版本控制的部署，并且扩展的集合。 这可能包括任何自治的每个微服务相关的数据库。

了解可以使用.NET 核心的实现的微服务体系结构的详细信息，请参阅可下载 PDF 电子书[.NET 微服务： 为容器化的.NET 应用程序的体系结构](https://aka.ms/microservicesebook)。 本指南也是可用[联机](../../microservices-architecture/index.md)。

但即使在微服务提供功能强大的功能独立于部署、 强子系统边界和技术多样性的方案中的它们也会引发许多新的挑战。 与分布式应用程序开发，例如分片和独立的数据模型; 相关面临的挑战实现弹性微服务; 之间的通信需要考虑最终一致性; 需要和操作的复杂性。 微服务引入更高级别的相比传统的整体应用程序的复杂性。

由于微服务体系结构的复杂性，只有特定方案和某些应用程序类型都适用于基于微服务构成的应用程序。 其中包括大型和复杂的应用程序有多个，不断演变的子系统。 在这些情况下，值得在更复杂的软件体系结构，用于增加的长期灵活性和效率更高的应用程序维护投资。 但对于不太复杂的方案，这可能是更好的做法继续整体应用程序方法，或者更简单的 N 层接近。

为最终请注意，即使的风险是重复这一概念，有关你不应查看在你的应用程序中使用微服务"一体化或 nothing 根本*。*" 可以扩展，还可以通过添加新的、 基于微服务的小型方案发展现有的单一应用程序。 你不必从头以开始使用的微服务体系结构方法开始。 事实上，我们建议你通过添加新的方案中使用现有的整体或 N 层应用程序演变。 最终，你可以将分解到自治组件或微服务应用程序。 你可以开始不断演变的微服务方向，执行步骤的整体应用程序。

## <a name="when-to-use-azure-app-service-for-modernizing-existing-net-apps"></a>何时为 modernizing 现有的.NET 应用程序使用 Azure App Service

当由于 web 应用程序已开发了使用.NET Framework 现代化的云进行优化的成熟度，到的现有 ASP.NET web 应用程序主要依赖项将显示在 Windows 和 Internet 信息服务器 (IIS)，最有可能。 你可以使用和部署基于 Windows 和基于 IIS 的应用程序通过直接部署到[Azure App Service](https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is)或第一台 containerizing 你的应用程序通过使用 Windows 容器。 如果 containerizing，或者部署应用程序到 Windows 容器承载 （基于 VM 的） 或到 Azure Service Fabric 群集支持的 Windows 容器。

当你使用 Windows 容器时，你将获取容器化的所有的优点。 提高了灵活性传送和部署你的应用，并减少环境问题 （过渡、 开发/测试、 生产） 的问题。 在下一步的几个部分中，我们进入有关你使用容器带来的好处的详细信息。

截止到撰写本指南中，Azure App Service 不支持 Windows 容器。 它适用于 Linux 支持容器。 因此，你下一步的问题可能是，"如何之间做出选择 Azure App Service 和 Windows 容器？"

基本上，如果 Azure App Service 适用于你的应用程序，并且不存在的任何服务器或阻止要使用 App Service 的路径的自定义依赖关系，你应迁移到 App Service 现有.NET web 应用程序。 这是维护你的应用程序的最简单、 最有效方法。 在 Azure 中，你的应用程序还将具有更简单的维护路径因为从 PaaS 的基础结构，如 DBaaS、 CaaS 和 STaaS 优势。

但是，如果你的应用程序确实具有服务器或不支持在 Azure App Service 中的自定义依赖关系，你可能需要考虑基于 Windows 容器的选项。 服务器或自定义的依赖项的示例包括第三方软件或.msi 文件，需要安装在服务器上，但它不在 Azure App Service 支持。 另一个示例是在 Azure App Service，不像使用 COM 对全局程序集缓存 (GAC) 中的程序集支持的任何其他服务器配置 / COM + 组件。 感谢 Windows 容器映像，你可以包含自定义依赖项的同一个"单位中部署。"

或者，你无法重构你的应用程序不支持的 Azure App Service 的区域。 具体取决于工作量重构都需要，你必须仔细评估，是否值得执行此操作。

### <a name="benefits-of-moving-to-azure-app-service"></a>将移动到 Azure App Service 的优点

Azure App Service 是完全托管的 PaaS 产品，可以轻松地生成由业务流程的 web 应用程序。 当你使用 App Service 时，则将避免与升级和维护 web 应用本地关联的基础结构管理成本。 具体而言，你将剪切的硬件和许可成本的 web 应用程序在本地运行。

如果你的 web 应用程序是时间的适用于迁移到 Azure App Service 的主要优势是时间的短移动应用程序所需量。 应用程序服务提供非常简单的环境，在其中吧。

Azure App Service 是大多数 web 应用的最佳选择，因为它是可用于运行 web 应用的 Azure 中最简单的 PaaS。 部署和管理集成到平台、 站点快速缩放以应对高流量负载，和内置的负载平衡和流量管理器提供高可用性。

即使监视你的 web 应用非常简单，通过 Azure Application Insights。 Application Insights 免费使用 App Service，附送，而且不需要在你的应用程序中编写任何特殊的代码。 只需在 App Service 中运行你的 web 应用，并且你将获取令人信服的监视系统，与任何额外工作。

使用 App Service，可以直接从 Azure Web 应用程序库 （如 WordPress 或 Umbraco），使用许多开放源代码应用程序或你可以使用的框架和您的选择，如 ASP.NET 工具来创建新的站点。 应用程序服务 web 作业功能，可轻松地为你的 App Service web 应用添加后台作业处理。

使用 Azure App Service Web Apps 功能迁移你的 web 应用的主要优点包括：

-   自动缩放以满足忙时的需求，并在静音时间内降低成本。

-   自动站点备份来保护更改和数据。

-   高可用性和在 Azure PaaS 平台上的恢复。

-   部署槽的开发和过渡环境，和测试多个站点设计。

-   负载平衡和分布式拒绝服务 (DDoS) 保护。

-   若要将用户定向到最近地理部署的流量管理。

尽管应用程序服务可能是新的 web 应用的最佳选择，但是，对于现有应用程序，App Service 可能是最佳选择仅当在 App Service 支持你的应用程序依赖关系。

### <a name="additional-resources"></a>其他资源

-   **对 Azure App Service 的兼容性分析**  
[https://www.migratetoazure.net/Resources](https://www.migratetoazure.net/Resources)


### <a name="benefits-of-moving-to-windows-containers"></a>将移动到 Windows 容器的优点

使用 Windows 容器的主要优势是，获得更加可靠和改进部署体验，相比非容器化应用程序。 此外，拥有有效地改进与容器应用程序可使你的应用程序供许多其他平台和支持 Windows 容器的云。 以下各节中更详细地介绍移动到 Windows 容器的好处。

支持 Windows 容器 （在正式发布，截至中旬 2017年） 的 Azure 中的主计算环境是 Azure Service Fabric 和基本 Windows 容器主机 (Windows Server 2016 Vm)。 这些环境是本指南中涉及的主要的基础结构方案。

你还可以部署 Windows 容器到其他 orchestrators，如 Kubernetes、 Docker Swarm，或 DC/OS。 当前 （尽早在 2017 年 1），这些平台处于预览状态 Azure 容器服务中使用 Windows 容器。

>[!div class="step-by-step"]
[上一页](microsoft-technologies-in-cloud-devops-ready-applications.md)
[下一页](how-to-deploy-existing-net-apps-to-azure-app-service.md)
