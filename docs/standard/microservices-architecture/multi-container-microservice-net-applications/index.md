---
title: 设计和开发基于微服务的多容器 .NET 应用程序
description: 容器化 .NET 应用程序的 .NET 微服务体系结构 | 了解用于设计和开发基于微服务的多容器 .NET 应用程序的外部体系结构。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 3bbf746aa9c0b66a097b8c4df2964b5679342fd0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144138"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a><span data-ttu-id="b24f7-103">设计和开发基于微服务的多容器 .NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="b24f7-103">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>

<span data-ttu-id="b24f7-104">开发容器化微服务应用程序意味着将生成多容器应用程序。*但是，多容器应用程序也可以更简单（例如三层应用程序），也可以不使用微服务体系结构生成。*</span><span class="sxs-lookup"><span data-stu-id="b24f7-104">*Developing containerized microservice applications means you are building multi-container applications. However, a multi-container application could also be simpler—for example, a three-tier application—and might not be built using a microservice architecture.*</span></span>

<span data-ttu-id="b24f7-105">之前我们提出了“生成微服务体系结构时 Docker 是否是必需的？”这一问题。</span><span class="sxs-lookup"><span data-stu-id="b24f7-105">Earlier we raised the question "Is Docker necessary when building a microservice architecture?"</span></span> <span data-ttu-id="b24f7-106">很显然，答案是否定。</span><span class="sxs-lookup"><span data-stu-id="b24f7-106">The answer is a clear no.</span></span> <span data-ttu-id="b24f7-107">Docker 是推动器，可以提供很多优势，但容器和 Docker 不属于微服务的硬性要求。</span><span class="sxs-lookup"><span data-stu-id="b24f7-107">Docker is an enabler and can provide significant benefits, but containers and Docker are not a hard requirement for microservices.</span></span> <span data-ttu-id="b24f7-108">例如，使用 Azure Service Fabric 时，它支持将微服务作为简单的流程或 Docker 容器运行，所以使用或不使用 Docker 都可以创建基于微服务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b24f7-108">As an example, you could create a microservices-based application with or without Docker when using Azure Service Fabric, which supports microservices running as simple processes or as Docker containers.</span></span>

<span data-ttu-id="b24f7-109">但是，如果知道如何设计和开发基于微服务，同时基于 Docker 容器的应用程序，将能够设计和开发任何其他更简单的应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="b24f7-109">However, if you know how to design and develop a microservices-based application that is also based on Docker containers, you will be able to design and develop any other, simpler application model.</span></span> <span data-ttu-id="b24f7-110">例如，可以设计还需要多容器方法的三层应用程序。</span><span class="sxs-lookup"><span data-stu-id="b24f7-110">For example, you might design a three-tier application that also requires a multi-container approach.</span></span> <span data-ttu-id="b24f7-111">鉴于此，另外还因为微服务体系结构是容器领域的重要趋势，本节会重点介绍如何使用 Docker 容器实现微服务体系结构。</span><span class="sxs-lookup"><span data-stu-id="b24f7-111">Because of that, and because microservice architectures are an important trend within the container world, this section focuses on a microservice architecture implementation using Docker containers.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b24f7-112">[上一页](../docker-application-development-process/docker-app-development-workflow.md)
>[下一页](microservice-application-design.md)</span><span class="sxs-lookup"><span data-stu-id="b24f7-112">[Previous](../docker-application-development-process/docker-app-development-workflow.md)
[Next](microservice-application-design.md)</span></span>