---
title: 实现使用指数退避算法的重试
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现使用指数退避算法的重试
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: e0758ee8fe28cb45ecd35ad07ddc738c12614973
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148764"
---
# <a name="implement-retries-with-exponential-backoff"></a>实现使用指数退避算法的重试

[使用指数退避算法的重试](https://docs.microsoft.com/azure/architecture/patterns/retry)是一种尝试重试操作的技术，等待时间呈指级增长，直到达到最大重试次数（[指数退避算法](https://en.wikipedia.org/wiki/Exponential_backoff)）。 该技术接受以下事实：云资源可能因任何原因而出现几秒钟以上的间歇性不可用情况。 例如，业务流程协调程序可能会将容器移动到群集中的另一个节点以进行负载均衡。 在此期间，某些请求可能会失败。 另一个实例是像 SQL Azure 这样的数据库，在该数据库中，数据库可以移动到另一台服务器进行负载均衡，这会导致数据库有几秒钟时间不可用。

有好几种方法可实现使用指数退避算法的重试逻辑。

>[!div class="step-by-step"]
>[上一页](partial-failure-strategies.md)
>[下一页](implement-resilient-entity-framework-core-sql-connections.md)