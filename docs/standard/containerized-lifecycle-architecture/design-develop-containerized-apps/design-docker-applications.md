---
title: Docker 应用程序设计
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 54f6f1ecdd89b85d4f44136da9a5ec9610f170a9
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="design-docker-applications"></a><span data-ttu-id="c4e0b-103">Docker 应用程序设计</span><span class="sxs-lookup"><span data-stu-id="c4e0b-103">Design Docker applications</span></span>

<span data-ttu-id="c4e0b-104">Chapter 1 引入了有关容器和 Docker 的基本概念。</span><span class="sxs-lookup"><span data-stu-id="c4e0b-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="c4e0b-105">该信息是信息的基本级别，请开始。</span><span class="sxs-lookup"><span data-stu-id="c4e0b-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="c4e0b-106">但是，企业应用程序可能十分复杂，而不是单个服务或容器的多个服务组成。</span><span class="sxs-lookup"><span data-stu-id="c4e0b-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="c4e0b-107">可选的使用情况下，你需要知道其他方法设计，如面向服务体系结构 (SOA) 和更高级的微服务概念和容器 orchestration 概念。</span><span class="sxs-lookup"><span data-stu-id="c4e0b-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="c4e0b-108">本文档的范围并不局限于微服务但到任何 Docker 应用程序生命周期，因此，它不会不浏览深度中的微服务体系结构还可以使用容器和 Docker 用于正则 SAO、 后台任务或作业，或甚至因为通过整体应用程序部署方法。</span><span class="sxs-lookup"><span data-stu-id="c4e0b-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="c4e0b-109">但是，我们将导入的应用程序生命周期和 DevOps 之前，有必要知道如何将对设计和构造你的应用程序和所选的设计是什么。</span><span class="sxs-lookup"><span data-stu-id="c4e0b-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c4e0b-110">[以前](index.md) [下一步] (常见的容器-设计-principles.md)</span><span class="sxs-lookup"><span data-stu-id="c4e0b-110">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
