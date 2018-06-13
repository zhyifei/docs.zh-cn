---
title: 有关云本机应用程序的新增功能？
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |有关云本机应用程序的新增功能？
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 0e880689001ece2b770811cfbe3fea43aa425b32
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957987"
---
# <a name="what-about-cloud-native-applications"></a>有关云本机应用程序的新增功能？

尽管[云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)应用程序不是主要关心的本指南中，是很有帮助，以便了解此现代化成熟度，从而区分从云优化应用程序。

图 4-3 将置于应用程序现代化成熟度云本机应用：

![定位云本机应用程序](./media/image3.png)

> **图 4-3。** 定位云本机应用程序

云本机现代化成熟度通常需要新的开发投资。 移至云本机级别通常是由驱动的业务需求来提升应用程序尽可能多地以极大地提高在通过创建可部署自治子系统 （微服务） 的大型应用程序的缩放和规模独立从应用程序同时提供的这些自治应用的部件的长术语和增加演变灵活性在降低成本的其他区域显著竞争优势。 

主要支柱[云本机](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)应用程序都基于微服务体系结构方法，可以借助灵活性不断变化，并且扩展到将会很难实现在整体体系结构中为部署的限制在本地或云环境。

图 4-4 显示云本机模型的主要特征。  

> ![云本机特征是微服务，容器，云弹性、 orchestrators 和 serverles](./media/image4.png)
>
> **图 4-4。** 云本机特征

此外，你可以通过添加其他服务，如人工智能 (AI)、 机器学习 (ML) 和 IoT 扩展基本现代应用 web 程序和云本机应用。 你可能使用这些服务的任何扩展任何可能的云优化方法。

在云本机级别的应用程序中的重要差别在于在应用程序体系结构。 [云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)应用程序是，根据定义，基于微服务的应用。 云本机应用需要特殊的体系结构、 技术和平台，相比整体 web 应用程序或传统的 N 层应用程序。

## <a name="cloud-native-applications-details"></a>云本机应用程序详细信息

[云本机](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)为大型和任务关键型应用程序的更高级或成熟状态。 云本机应用程序通常需要体系结构和设计而不是从头创建的 modernizing 现有应用程序。 云本机应用程序和一个更简单的云优化 web 应用的主要区别是用于在云本机方法中的微服务体系结构的建议。 云优化应用也可以是单一的 web 应用或 N 层应用程序。

[十二个因素应用](https://12factor.net/)（密切相关到微服务方法的模式的集合） 也被视为一项要求[云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)应用程序体系结构。

[云本机计算 Foundation (CNCF)](https://www.cncf.io/)是云本机原则主提升程序。 Microsoft 是[CNCF 成员](https://azure.microsoft.com/blog/announcing-cncf/)。

有关示例定义和特征的云本机应用程序的详细信息，请参阅 Gartner 文章[如何构建和设计云本机应用程序](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)。 有关如何实现云本机应用程序从 Microsoft 的具体指引，请参阅[.NET 微服务： 为容器化的.NET 应用程序的体系结构](https://aka.ms/microservicesebook)。

要考虑是否你迁移到完整的应用程序，最重要的因素[云本机](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms)模型是你必须构建到基于微服务的体系结构。 这清楚地由于涉及的大型重构过程需要大量的开发。 选择此选项，通常是任务关键型应用程序需要更高级别的可伸缩性和长期的灵活性。 但是，你可以开始在移至云本机通过添加只需少量的新方案的微服务并最终重构完全作为微服务应用程序。 这是递增的方法是在某些情况下的最佳选项。

## <a name="what-about-microservices"></a>有关微服务的新增功能？ 

在为你的组织考虑云本机应用程序，了解微服务以及它们如何工作非常重要。

微服务体系结构是可用于从零开始或发展向云本机应用程序的现有应用程序创建的应用程序的高级的方法。 你可以通过将几个微服务添加到现有应用程序若要了解有关新的微服务范例。 但很显然，你需要的架构师和代码，尤其是对于这种体系结构的方法。

但是，微服务并不是强制的任何新的或现代应用程序。 微服务不是"幻项目符号，"，并且它们不创建每个应用程序的单一的最佳方法。 如何以及何时使用微服务取决于生成所需的应用程序的类型。

微服务体系结构已变得分布式和大型或复杂的任务关键型应用程序基于自治服务形式的多个独立子系统的首选的方法。 在基于微服务的体系结构，应用程序生成为一个服务可以是独立开发、 测试、 版本控制的部署，并且扩展的集合。 这可能包括任何自治的每个微服务相关的数据库。

了解可以使用.NET 核心的实现的微服务体系结构的详细信息，请参阅可下载 PDF 电子书[.NET 微服务： 为容器化的.NET 应用程序的体系结构](https://aka.ms/microservicesebook)。 本指南也是可用[联机](../../microservices-architecture/index.md)。

但即使在微服务提供功能强大的功能独立于部署、 强子系统边界和技术多样性的方案中的它们也会引发许多新的挑战。 与分布式应用程序开发，例如分片和独立的数据模型; 相关面临的挑战实现弹性微服务; 之间的通信需要考虑最终一致性; 需要和操作的复杂性。 微服务引入更高级别的相比传统的整体应用程序的复杂性。

由于微服务体系结构的复杂性，只有特定方案和某些应用程序类型都适用于基于微服务构成的应用程序。 其中包括大型和复杂的应用程序有多个，不断演变的子系统。 在这些情况下，值得在更复杂的软件体系结构，用于增加的长期灵活性和效率更高的应用程序维护投资。 但对于不太复杂的方案，这可能是更好的做法继续整体应用程序方法，或者更简单的 N 层接近。

为最终请注意，即使的风险是重复这一概念，有关你不应查看在你为"一体化或 nothing 根本。"的应用程序中使用微服务 可以扩展，还可以通过添加新的、 基于微服务的小型方案发展现有的单一应用程序。 你不必从头以开始使用的微服务体系结构方法开始。 事实上，我们建议你通过添加新的方案中使用现有的整体或 N 层应用程序演变。 最终，你可以将分解到自治组件或微服务应用程序。 你可以开始不断演变的微服务方向，执行步骤的整体应用程序。

在任何情况下，此存在指南的其余部分侧重大部分所有上的"没有基于微服务的应用程序"，因为本指南主要面向的现有应用程序通常具有整体或 N 层体系结构的现代化。


>[!div class="step-by-step"]
[上一页](microsoft-technologies-in-cloud-optimized-applications.md)
[下一页](deploy-existing-net-apps-as-windows-containers.md)
