---
title: "实现重试使用指数退让"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现重试使用指数退让"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8ad8c6363ddff59915efc076161fe6b76074bbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a>实现重试使用指数退让

[*使用指数退让重试*](https://docs.microsoft.com/azure/architecture/patterns/retry)是尝试重试操作，使用按指数增长的等待时间，直到已达到最大重试计数技术 ([指数退让](https://en.wikipedia.org/wiki/Exponential_backoff)). 此方法包含这样一个事实，云资源间歇性可能不可用超过几秒钟出于任何原因。 例如，orchestrator 可能要转向容器进行负载平衡群集中的另一个节点。 在此期间，某些请求可能会失败。 另一个示例可能像 SQL Azure，其中的数据库可以被移到另一台服务器对于负载平衡，从而导致数据库可以在几秒内不可用的数据库。

有许多方法可以实现具有指数回退重试逻辑。


>[!div class="step-by-step"]
[以前](部分的失败-strategies.md) [下一步] (implement-resilient-entity-framework-core-sql-connections.md)
