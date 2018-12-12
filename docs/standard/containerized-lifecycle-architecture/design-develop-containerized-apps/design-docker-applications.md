---
title: 设计 Docker 应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: d02cec0595024eb7bd7c0ac46df093359680da74
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155374"
---
# <a name="design-docker-applications"></a><span data-ttu-id="7b54a-103">设计 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="7b54a-103">Design Docker applications</span></span>

<span data-ttu-id="7b54a-104">第 1 章引入了有关容器和 Docker 的基本概念。</span><span class="sxs-lookup"><span data-stu-id="7b54a-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="7b54a-105">该信息是信息的基本的入门所需。</span><span class="sxs-lookup"><span data-stu-id="7b54a-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="7b54a-106">但是，企业应用程序可能很复杂并且的而不是单个服务或容器的多个服务组成。</span><span class="sxs-lookup"><span data-stu-id="7b54a-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="7b54a-107">可选的使用情况下，您需要知道其他方法设计，如面向服务体系结构 (SOA) 和更高级的微服务概念和容器业务流程的概念。</span><span class="sxs-lookup"><span data-stu-id="7b54a-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="7b54a-108">本文档的范围并不局限于微服务，但到任何 Docker 应用程序生命周期，因此，它不会不探索深入的微服务体系结构还可以使用容器和 Docker 与正则圣保罗、 后台任务或作业，或甚至因为与整体式应用程序部署方法。</span><span class="sxs-lookup"><span data-stu-id="7b54a-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="7b54a-109">但是，在我们开始了解应用程序生命周期和 DevOps 之前，务必要知道如何将设计并构建您的应用程序和设计选项是什么。</span><span class="sxs-lookup"><span data-stu-id="7b54a-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7b54a-110">[上一页](index.md)
>[下一页](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="7b54a-110">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>