---
title: 实现使用指数退避算法的重试
description: 了解如何使用指数退避算法实现重试。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 421a4535888f432974c764b238c06b5b323aefb3
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362075"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="e889d-103">实现使用指数退避算法的重试</span><span class="sxs-lookup"><span data-stu-id="e889d-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="e889d-104">[*使用指数退避算法的重试*](/azure/architecture/patterns/retry)是一种重试操作方法，随着等待时间以指数方式增长，重试次数达到最大值（[指数退避算法](https://en.wikipedia.org/wiki/Exponential_backoff)）。</span><span class="sxs-lookup"><span data-stu-id="e889d-104">[*Retries with exponential backoff*](/azure/architecture/patterns/retry) is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="e889d-105">该技术接受以下事实：云资源可能因任何原因而出现几秒钟以上的间歇性不可用情况。</span><span class="sxs-lookup"><span data-stu-id="e889d-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="e889d-106">例如，业务流程协调程序可能会将容器移动到群集中的另一个节点以进行负载均衡。</span><span class="sxs-lookup"><span data-stu-id="e889d-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="e889d-107">在此期间，某些请求可能会失败。</span><span class="sxs-lookup"><span data-stu-id="e889d-107">During that time, some requests might fail.</span></span> <span data-ttu-id="e889d-108">另一个实例是像 SQL Azure 这样的数据库，在该数据库中，数据库可以移动到另一台服务器进行负载均衡，这会导致数据库有几秒钟时间不可用。</span><span class="sxs-lookup"><span data-stu-id="e889d-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="e889d-109">有好几种方法可实现使用指数退避算法的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="e889d-109">There are many approaches to implement retries logic with exponential backoff.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e889d-110">[上一页](partial-failure-strategies.md)
>[下一页](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="e889d-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>