---
title: 设计 Docker 应用程序
description: 查找此处参考微服务体系结构的深入指南，因为这是一个主题，它不本指南中详述。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 858147883b3b4a5a5f487856028fdbfa84f6cca9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675181"
---
# <a name="design-docker-applications"></a><span data-ttu-id="846d6-103">设计 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="846d6-103">Design Docker applications</span></span>

<span data-ttu-id="846d6-104">第 1 章引入了有关容器和 Docker 的基本概念。</span><span class="sxs-lookup"><span data-stu-id="846d6-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="846d6-105">该信息是信息的基本的入门所需。</span><span class="sxs-lookup"><span data-stu-id="846d6-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="846d6-106">但是，企业应用程序可能很复杂并且的而不是单个服务或容器的多个服务组成。</span><span class="sxs-lookup"><span data-stu-id="846d6-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="846d6-107">可选的使用情况下，您需要知道其他方法设计，如面向服务体系结构 (SOA) 和更高级的微服务概念和容器业务流程的概念。</span><span class="sxs-lookup"><span data-stu-id="846d6-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="846d6-108">本文档的范围并不局限于微服务，但到任何 Docker 应用程序生命周期，因此，它不会不探索深入的微服务体系结构还可以使用容器和 Docker 与常规 SOA、 后台任务或作业，或甚至因为与整体式应用程序部署方法。</span><span class="sxs-lookup"><span data-stu-id="846d6-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="846d6-109">**详细信息**若要了解有关企业应用程序和微服务体系结构深入的详细信息，请阅读指南[.NET 微服务：适用于容器化.NET 应用程序体系结构](https://docs.microsoft.com/dotnet/standard/microservices-architecture)，还可以从下载<https://aka.ms/MicroservicesEbook>。</span><span class="sxs-lookup"><span data-stu-id="846d6-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="846d6-110">但是，在我们开始了解应用程序生命周期和 DevOps 之前，务必要知道如何将设计并构建您的应用程序和设计选项是什么。</span><span class="sxs-lookup"><span data-stu-id="846d6-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="846d6-111">[上一页](index.md)
>[下一页](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="846d6-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
