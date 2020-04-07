---
title: 云本机的候选应用
description: 了解哪些类型的应用程序受益于云原生方法
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805609"
---
# <a name="candidate-apps-for-cloud-native"></a>云本机的候选应用

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

查看产品组合中的应用程序。 其中有多少人有资格获得云原生架构？ 它们全部？ 也许有些？

应用成本/收益分析，大多数人很可能不支持云原生所需的高昂价格标签。 云原生成本将远远超过应用程序的业务价值。

哪种应用程序可能是云本机的候选类型？

- 需要不断发展业务能力/功能的大型战略企业系统

- 需要高释放速度的应用程序 - 高度置信度

- 具有单个功能且无需完全重新部署整个系统*即可发布的系统*

- 由具有不同技术堆栈专业知识的团队开发的应用程序

- 具有必须独立扩展的组件的应用程序

然后是遗留系统。 虽然我们都希望构建新的应用程序，但我们通常负责实现对业务至关重要的遗留工作负载的现代化。 随着时间的推移，旧应用程序可以分解为微服务，容器化，并最终"重新平台"到云本机体系结构。

### <a name="modernizing-legacy-apps"></a>现代化传统应用

免费的 Microsoft 电子书[使用 Azure 云和 Windows 容器对现有 .NET 应用程序进行现代化改造](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)，为将本地工作负载迁移到云提供了指南。 图 1-10 显示了没有一种单一、一刀切的策略来实现旧应用程序的现代化。

![迁移旧工作负载的策略](./media/strategies-for-migrating-legacy-workloads.png)

**图 1-10**. 迁移旧工作负载的策略

非关键应用主要受益于快速提升和移动 （[云基础架构就绪](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)） 迁移。 在这里，本地工作负载将重新托管到基于云的 VM，无需更改。 此方法使用[IaaS（基础设施即服务）模型](https://azure.microsoft.com/overview/what-is-iaas/)。 Azure 包括多个工具，如[Azure 迁移](https://azure.microsoft.com/services/azure-migrate/)[、Azure 站点恢复](https://azure.microsoft.com/services/site-recovery/)和[Azure 数据库迁移服务](https://azure.microsoft.com/campaigns/database-migration/)，以便更轻松地移动。 虽然这种策略可以节省一些成本，但此类应用程序通常不是为解锁和利用云计算的优势而构建的。

对业务至关重要的单一应用通常受益于增强的提升和移位 （*云优化*） 迁移。 此方法包括启用关键云服务的部署优化 ， 而无需更改应用程序的核心体系结构。 例如，您可以将应用程序[容器化](https://docs.microsoft.com/virtualization/windowscontainers/about/)，并将其部署到容器协调器，如本书后面讨论的[Azure Kubernetes 服务](https://azure.microsoft.com/services/kubernetes-service/)。 进入云后，应用程序可能会使用其他云服务，如数据库、消息队列、监视和分布式缓存。

最后，执行战略企业功能的单一应用可能最好受益于*云原生*方法，这是本书的主题。 此方法提供敏捷性和速度。 但是，它的代价是重新平台、重新构建和重写代码。

如果您和您的团队认为云原生方法是适当的，则您应该与组织一起使决策合理化。 云原生方法将解决的业务问题究竟是什么？ 它如何与业务需求保持一致？

- 快速发布功能，增强信心？

- 细粒度可扩展性 - 更有效地使用资源？

- 提高系统弹性？

- 提高系统性能？

- 对操作的更多可见性？

- 混合开发平台和数据存储，以找到最适合作业的工具？

- 面向未来的应用投资？

正确的迁移策略取决于组织优先级和您所针对的系统。 对许多人来说，云优化单片应用程序或向 N-Tier 应用添加粗粒度服务可能更具成本效益。 在这些情况下，您仍然可以充分利用云 PaaS 功能，如 Azure 应用服务提供的功能。

## <a name="summary"></a>总结

在本章中，我们介绍了云原生计算。 我们提供了一个定义以及驱动云本机应用程序的关键功能。 我们研究了可能证明这种投资和努力合理的应用程序类型。

在介绍之后，我们现在将深入探讨云原生。

### <a name="references"></a>参考

- [云原生计算基金会](https://www.cncf.io/)

- [.NET 微服务：容器化 .NET 应用程序的体系结构](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [使用 Azure 云和 Windows 容器对现有 .NET 应用程序进行现代化](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [科妮莉亚·戴维斯的云原生模式](https://www.manning.com/books/cloud-native-patterns)

- [超越十二因素应用](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [什么是基础架构作为代码](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [优步工程的微观部署：自信地每天部署](https://eng.uber.com/micro-deploy/)

- [Netflix 如何部署代码](https://www.infoq.com/news/2013/06/netflix/)

- [用于扩展微信微服务的过载控制](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[上一页](definition.md)
>[下一页](introduce-eshoponcontainers-reference-app.md)
