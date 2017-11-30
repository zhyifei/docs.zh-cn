---
title: "Docker 应用程序设计"
description: "使用 Microsoft 平台和工具的 Docker 容器化应用程序生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: db8376abf95aab51fad23f4b351cb772351117ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="design-docker-applications"></a><span data-ttu-id="24989-104">Docker 应用程序设计</span><span class="sxs-lookup"><span data-stu-id="24989-104">Design Docker applications</span></span>

<span data-ttu-id="24989-105">Chapter 1 引入了有关容器和 Docker 的基本概念。</span><span class="sxs-lookup"><span data-stu-id="24989-105">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="24989-106">该信息是信息的基本级别，请开始。</span><span class="sxs-lookup"><span data-stu-id="24989-106">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="24989-107">但是，企业应用程序可能十分复杂，而不是单个服务或容器的多个服务组成。</span><span class="sxs-lookup"><span data-stu-id="24989-107">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="24989-108">可选的使用情况下，你需要知道其他方法设计，如面向服务体系结构 (SOA) 和更高级的微服务概念和容器 orchestration 概念。</span><span class="sxs-lookup"><span data-stu-id="24989-108">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="24989-109">本文档的范围并不局限于微服务但到任何 Docker 应用程序生命周期，因此，它不会不浏览深度中的微服务体系结构还可以使用容器和 Docker 用于正则 SAO、 后台任务或作业，或甚至因为通过整体应用程序部署方法。</span><span class="sxs-lookup"><span data-stu-id="24989-109">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="24989-110">但是，我们将导入的应用程序生命周期和 DevOps 之前，有必要知道如何将对设计和构造你的应用程序和所选的设计是什么。</span><span class="sxs-lookup"><span data-stu-id="24989-110">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="24989-111">[以前](index.md) [下一步] (常见的容器-设计-principles.md)</span><span class="sxs-lookup"><span data-stu-id="24989-111">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
