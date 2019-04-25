---
title: 实现具有恢复能力的应用程序
description: 了解恢复能力，这是微服务体系结构中的核心概念。 必须了解如何适当地处理瞬间失败，因为将会发生这些失败。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 00724509ba6e027ef73f72bfb6f85b8ec0aa9d25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977693"
---
# <a name="implement-resilient-applications"></a>实现可复原的应用程序

微服务和基于云的应用程序必须允许最终必然会发生的部分故障。*必须设计应用程序，使其可从这些部分失败中恢复。*

恢复能力是指从故障中恢复并继续工作的能力。 这并不是指避免失败，而是接受会发生失败这一事实，并以能够避免停机或数据丢失的方式对失败做出响应。 恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。

设计和部署基于微服务的应用程序已经非常具有挑战性。 然而还需要让应用程序在必然发生某种故障的环境中保持正常运行。 因此，应用程序应具有恢复能力。 应将其设计为能够处理部分故障，如网络中断或者云中节点或 VM 故障。 甚至将微服务（容器）移动到群集内的另一个节点，也可能导致应用程序出现间歇性的功能短缺故障。

应用程序的各个组件还应涵盖运行状况监视功能。 遵循本章节中的准则，可创建这样的应用程序：即使在基于云的复杂部署中出现短暂停机或暂时中断，它也能平稳运行。

>[!div class="step-by-step"]
>[上一页](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[下一页](handle-partial-failure.md)