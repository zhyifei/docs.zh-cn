---
title: 利用无服务器函数
description: 在云本机应用程序中利用无服务器和 Azure Functions
ms.date: 06/30/2019
ms.openlocfilehash: 77ddef0eb8844ea1b55cd2fc5ec8aa12593c8631
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841743"
---
# <a name="leveraging-serverless-functions"></a>利用无服务器函数

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

在管理要利用云功能的完整计算机和操作系统的各种领域，无服务器生活在极端的最终位置，即你的代码，你只需在代码运行时付费。 Azure Functions 提供了一种将无服务器功能构建到应用程序中的方法。

## <a name="what-is-serverless"></a>什么是无服务器？

无服务器计算并不意味着在运行应用程序时不涉及到服务器-代码仍在某个服务器上运行。 不同之处在于，应用程序开发团队不再需要关注管理服务器基础结构。 无服务器计算解决方案，如 Azure Functions 帮助团队提高其工作效率，并使组织能够优化其资源并专注于交付解决方案。

无服务器计算使用事件触发的无状态容器来承载应用程序或应用程序的一部分。 无服务器平台可以横向扩展和扩展，以满足需求。 Azure Functions 的平台可以轻松直接访问其他 Azure 服务（如队列、事件和存储）。

## <a name="what-challenges-are-solved-by-serverless"></a>无服务器解决了哪些问题？

无服务器是运行自己的硬件的终极抽象。 开发人员可以专注于编写代码来解决业务问题，而无需考虑在托管您自己的服务器时可能已经需要的以下任何任务：

- 购买计算机和软件许可证
- 承载、保护、配置和维护计算机及其网络、电源和/C 要求
- 修补和升级操作系统和软件
- 将 web 服务器或计算机服务配置为托管应用程序软件
- 在其平台中配置应用程序软件

许多公司都使用几十个员工并分配大量预算来支持这些硬件基础结构问题。 只需迁移到云即可消除其中一些问题;将应用程序切换到无服务器的所有方法均可消除其余部分。

## <a name="what-scenarios-are-appropriate-for-serverless"></a>哪些方案适用于无服务器？

无服务器使用为响应某些触发器而调用的单独的短时间运行的函数。 这使它们非常适合用于处理后台任务。

例如，应用程序可能需要在处理请求的过程中发送电子邮件。 不是在处理 web 请求的过程中发送电子邮件，而是将电子邮件的详细信息放置到队列中，而 Azure 函数可用于提取邮件并发送电子邮件。 应用程序的许多不同部分甚至许多应用程序都可以利用这一相同的 Azure 功能，为应用程序提供改进的性能和可伸缩性，并使用[基于队列的负载调节](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling)来避免与发送电子邮件相关的瓶颈。

尽管应用程序和 Azure Functions 之间的[发行者/订户模式](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber)是最常见的模式，但也可以使用其他模式。 其他事件（如对 Azure Blob 存储的更改）可以触发 Azure Functions。 支持图像上传的应用程序可能有一个 Azure 函数负责创建缩略图图像，或者将上传的图像大小调整为一致的维度，或者优化图像大小。 所有此功能都可通过插入到 Azure Blob 存储直接触发，使复杂性和工作负荷超出应用程序本身。

许多应用程序将长时间运行的进程作为工作流的一部分。 通常，这些任务在用户与应用程序交互的过程中完成，并强制用户等待并对其体验产生负面影响。 无服务器计算提供在用户交互循环之外执行缓慢任务的极佳方法，这些任务可轻松地按需求进行缩放，而无需整个应用程序进行缩放。

## <a name="when-should-you-avoid-serverless"></a>何时应避免无服务器服务器？

对于不阻止用户界面的任务，最好使用无服务器计算。 这意味着它们并不适合直接托管 web 应用程序或 web Api。 导致这种情况的主要原因是，无服务器解决方案按需预配和缩放。 如果需要函数的新实例（称为*冷启动*），则需要花时间进行设置。 此时间通常是几秒钟，但可能会更长，具体取决于各种因素。 单个实例经常会无限期地保持活动状态（例如，通过定期向其发出请求），但如果需要增加实例的数量，则会保留冷启动问题。

![冷启动](./media/cold-start-warm-start.png)
**图 3-10**。 冷启动和热启动。

如果需要完全避免冷启动，可以选择从[消耗计划切换到专用计划](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)。 你还可以[配置一个或多个](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)具有高级计划的预准备好实例，因此，当你需要添加另一个实例时，该实例已准备就绪，可以继续。 这些选项可以减少与无服务器计算相关的关键问题之一。

对于长时间运行的任务，通常还应避免无服务器。 它们最适用于可以快速完成的小型工作。 大多数无服务器平台需要在几分钟内完成单个功能。 Azure Functions 默认为5分钟的超时持续时间（最多可以配置10分钟）。 Azure Functions 高级计划还可以缓解此问题，默认情况下超时为30分钟，并允许配置无限大限制。

最后，为应用程序中的某些任务利用无服务器，增加了复杂性。 通常情况下，最好先以模块化、松散耦合的方式构建应用程序，然后确定是否有无服务器可提供的好处，这使得额外的复杂性更值得。 许多较小的应用程序在单一单一部署中运行良好，无需分布式应用程序体系结构的无服务器计算要求。

## <a name="references"></a>reference

- [了解无服务器冷启动](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [准备好 Azure Functions 实例](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [在 Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)

>[!div class="step-by-step"]
>[上一页](leverage-containers-orchestrators.md)
>[下一页](combine-containers-serverless-approaches.md)
