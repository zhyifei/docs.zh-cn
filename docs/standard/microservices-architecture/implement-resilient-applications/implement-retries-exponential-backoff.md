---
title: 实现使用指数退避算法的重试
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现使用指数退避算法的重试
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 7f909c6f81abce80bfdf118112271f1f87254793
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571418"
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="a0b66-103">实现使用指数退避算法的重试</span><span class="sxs-lookup"><span data-stu-id="a0b66-103">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="a0b66-104">[使用指数退避算法的重试](https://docs.microsoft.com/azure/architecture/patterns/retry)是一种尝试重试操作的技术，等待时间呈指级增长，直到达到最大重试次数（[指数退避算法](https://en.wikipedia.org/wiki/Exponential_backoff)）。</span><span class="sxs-lookup"><span data-stu-id="a0b66-104">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="a0b66-105">该技术接受以下事实：云资源可能因任何原因而出现几秒钟以上的间歇性不可用情况。</span><span class="sxs-lookup"><span data-stu-id="a0b66-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="a0b66-106">例如，业务流程协调程序可能会将容器移动到群集中的另一个节点以进行负载均衡。</span><span class="sxs-lookup"><span data-stu-id="a0b66-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="a0b66-107">在此期间，某些请求可能会失败。</span><span class="sxs-lookup"><span data-stu-id="a0b66-107">During that time, some requests might fail.</span></span> <span data-ttu-id="a0b66-108">另一个实例是像 SQL Azure 这样的数据库，在该数据库中，数据库可以移动到另一台服务器进行负载均衡，这会导致数据库有几秒钟时间不可用。</span><span class="sxs-lookup"><span data-stu-id="a0b66-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="a0b66-109">有好几种方法可实现使用指数退避算法的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="a0b66-109">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="a0b66-110">[上一篇] (partial-failure-strategies.md) [下一篇] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="a0b66-110">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
