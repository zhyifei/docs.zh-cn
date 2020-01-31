---
title: 云本机复原能力
description: 构建适用于 Azure 的云本机 .NET 应用 |云本机复原
ms.date: 06/30/2019
ms.openlocfilehash: 427405d95534c4467ab519c2188fe88e2f18e2b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781089"
---
# <a name="cloud-native-resiliency"></a>云本机复原能力

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

复原能力是指系统能够应对故障，并仍能正常工作。 这并不是为了避免失败。 但这就是在基于云的系统中接受该故障是不可避免的，并生成应用程序来响应它。 复原的最终目标是在故障后将应用程序恢复到完全正常运行的状态。

与传统的单一应用程序不同，在一个进程中，一切都一起运行，云本机系统采用分布式体系结构，如图6-1 所示：

![分布式云-本机环境](./media/distributed-cloud-native-environment.png)

**图 6-1**。 分布式云-本机环境

在上图中，请注意每个客户端、微服务和基于云的[后备服务](https://12factor.net/backing-services)如何作为单独的进程运行，跨不同的服务器运行，并通过基于网络的调用进行通信。

那么，会出现什么问题呢？

- 意外的[网络延迟](https://www.techopedia.com/definition/8553/network-latency)。
- [暂时性故障](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults)（暂时性网络连接错误）。
- 由长时间运行的同步操作阻止。
- 已崩溃并且正在重新启动或移动的主机进程。
- 一段时间后无法响应的重载微服务。
- 正在进行的 DevOps 操作，例如更新或缩放操作。
- Orchestrator 操作，如将服务从一个节点移到另一个节点。
- 商用硬件发生硬件故障。

在将分布式服务部署到基于云的基础结构中时，先前列表中的因素非常真实，你必须构建保守来处理它们。

在小规模的分布式系统中，故障不会频繁，但随着系统的扩大和缩小，你可能会在部分故障变为正常操作时遇到更多的问题。

因此，您的应用程序和基础结构必须具有复原能力。 在以下部分中，我们将探讨可添加到应用程序中的防御性技术，以及可以利用的内置云功能，以帮助你对用户体验进行验证。

>[!div class="step-by-step"]
>[上一页](elastic-search-in-azure.md)
>[下一页](application-resiliency-patterns.md)
