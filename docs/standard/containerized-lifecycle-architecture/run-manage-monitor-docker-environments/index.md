---
title: 运行、管理和监视 Docker 生产环境
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 41c170b5e58d92c6e669de48c1f41caf5b2aa6e8
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="37ecc-103">运行、管理和监视 Docker 生产环境</span><span class="sxs-lookup"><span data-stu-id="37ecc-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="37ecc-104">远景：企业应用程序需要具有高可用性和高可伸缩性；IT 操作需要能够管理和监视环境及应用程序本身。</span><span class="sxs-lookup"><span data-stu-id="37ecc-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="37ecc-105">容器化 Docker 应用程序生命周期的最后一个关键点在于，如何能够在可缩放的高可用性 (HA) 生产环境中运行、管理和监视应用程序。</span><span class="sxs-lookup"><span data-stu-id="37ecc-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="37ecc-106">如何在生产环境中运行容器化应用程序（基础体系结构和平台技术）也与此电子书第 1 章中介绍的选定基础结构和开发平台密切相关，并完全建立在这些基础结构和平台的基础之上。</span><span class="sxs-lookup"><span data-stu-id="37ecc-106">How you run your containerized applications in production (infrastructure architecture and platform technologies) is also very much related and completely founded on the chosen architecture and development platforms that we looked at in the Chapter 1 of this e-book.</span></span> <span data-ttu-id="37ecc-107">本章检验 Microsoft 和其他供应商提供的、可用于有效运行高度可伸缩的 HA 分布式应用程序的特定产品和技术，并介绍如何从 IT 视角管理和监视它们。</span><span class="sxs-lookup"><span data-stu-id="37ecc-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run highly scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="37ecc-108">[上一页] (../docker-devops-workflow/docker-application-outer-loop-devops-workflow.md) [下一页] (run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="37ecc-108">[Previous] (../docker-devops-workflow/docker-application-outer-loop-devops-workflow.md) [Next] (run-microservices-based-applications-in-production.md)</span></span>
