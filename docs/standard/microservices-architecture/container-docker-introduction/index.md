---
title: 容器和 Docker 简介
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 容器和 Docker 简介
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: c1f78a8904270123188367a01bddbcac3f7f1b7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="6300b-103">容器和 Docker 简介</span><span class="sxs-lookup"><span data-stu-id="6300b-103">Introduction to Containers and Docker</span></span>

<span data-ttu-id="6300b-104">容器化是软件开发的一种方法，通过该方法可将应用程序或服务、其依赖项及其配置（抽象化为部署清单文件）一起打包为容器映像。</span><span class="sxs-lookup"><span data-stu-id="6300b-104">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="6300b-105">容器化应用程序可以作为一个单元进行测试，并可以作为容器映像实例部署到主机操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="6300b-105">The containerized application can be tested as a unit and deployed as a container image instance to the host operating system (OS).</span></span>

<span data-ttu-id="6300b-106">就像船只、火车或卡车运输货运容器而不论其内部的货物一样，软件容器充当软件的标准单元，其中可以包含不同的代码和依赖项。</span><span class="sxs-lookup"><span data-stu-id="6300b-106">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="6300b-107">按照这种方式容器化软件，开发人员和 IT 专业人员只需进行极少修改或不修改，即可将其部署到不同的环境。</span><span class="sxs-lookup"><span data-stu-id="6300b-107">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="6300b-108">容器还会在共享 OS 上将应用程序彼此隔离开。</span><span class="sxs-lookup"><span data-stu-id="6300b-108">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="6300b-109">容器化应用程序在容器主机上运行，而容器主机在 OS（Linux 或 Windows）上运行。</span><span class="sxs-lookup"><span data-stu-id="6300b-109">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="6300b-110">因此，容器的占用比虚拟机 (VM) 映像小得多。</span><span class="sxs-lookup"><span data-stu-id="6300b-110">Containers therefore have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="6300b-111">每个容器可以运行整个 Web 应用或服务，如图 2-1 所示。</span><span class="sxs-lookup"><span data-stu-id="6300b-111">Each container can run a whole web application or a service, as shown in Figure 2-1.</span></span> <span data-ttu-id="6300b-112">在此示例中，Docker 主机是容器主机，而 App1、App2、Svc 1 和 Svc 2 是容器化应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="6300b-112">In this example, Docker host is a container host, and App1, App2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

![](./media/image1.png)

<span data-ttu-id="6300b-113">**图 2-1**.</span><span class="sxs-lookup"><span data-stu-id="6300b-113">**Figure 2-1**.</span></span> <span data-ttu-id="6300b-114">在一个容器主机上运行多个容器</span><span class="sxs-lookup"><span data-stu-id="6300b-114">Multiple containers running on a container host</span></span>

<span data-ttu-id="6300b-115">容器化的另一个优势在于可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="6300b-115">Another benefit of containerization is scalability.</span></span> <span data-ttu-id="6300b-116">通过为短期任务创建新容器，可以快速扩大。</span><span class="sxs-lookup"><span data-stu-id="6300b-116">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="6300b-117">从应用程序的角度来看，实例化映像（创建容器）类似于实例化 服务或 Web 应用等进程。</span><span class="sxs-lookup"><span data-stu-id="6300b-117">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="6300b-118">但出于可靠性考虑，在多个主机服务器上运行同一映像的多个实例时，通常要使每个容器（映像实例）在不同容错域中的不同主机服务器或 VM 中运行。</span><span class="sxs-lookup"><span data-stu-id="6300b-118">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="6300b-119">总而言之，容器在整个应用程序生命周期工作流中提供以下优点：隔离性、可移植性、灵活性、可伸缩性和可控性。</span><span class="sxs-lookup"><span data-stu-id="6300b-119">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the whole application lifecycle workflow.</span></span> <span data-ttu-id="6300b-120">最重要的优点是可在开发和操作之间提供隔离。</span><span class="sxs-lookup"><span data-stu-id="6300b-120">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6300b-121">[上一页] (../index.md) [下一页] (docker-defined.md)</span><span class="sxs-lookup"><span data-stu-id="6300b-121">[Previous] (../index.md) [Next] (docker-defined.md)</span></span>
