---
title: 容器和 Docker 简介
description: 获取使用 Docker 的主要优势的高级别概述。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: aa3ead1cb184e23dd091822368e62f580ed73ee5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785616"
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="7d766-103">容器和 Docker 简介</span><span class="sxs-lookup"><span data-stu-id="7d766-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="7d766-104">*容器化是在其中应用程序或服务、 其依赖项，以及其配置 （抽象化为部署清单文件） 一起打包为容器映像的软件开发方法。然后可以测试容器化应用程序作为一个单元并将其部署为容器映像实例对主机操作系统 (OS)。*</span><span class="sxs-lookup"><span data-stu-id="7d766-104">*Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image. You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system (OS).*</span></span>

<span data-ttu-id="7d766-105">就像船只、火车或卡车运输集装箱而不论其内部的货物一样，软件容器充当软件部署的标准单元，其中可以包含不同的代码和依赖项。</span><span class="sxs-lookup"><span data-stu-id="7d766-105">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software deployment that can contain different code and dependencies.</span></span> <span data-ttu-id="7d766-106">按照这种方式容器化软件，开发人员和 IT 专业人员只需进行极少修改或不修改，即可将其部署到不同的环境。</span><span class="sxs-lookup"><span data-stu-id="7d766-106">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="7d766-107">容器还会在共享 OS 上将应用程序彼此隔离开。</span><span class="sxs-lookup"><span data-stu-id="7d766-107">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="7d766-108">容器化应用程序在容器主机上运行，而容器主机在 OS（Linux 或 Windows）上运行。</span><span class="sxs-lookup"><span data-stu-id="7d766-108">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="7d766-109">因此，容器具有太多占用比虚拟机 (VM) 映像小。</span><span class="sxs-lookup"><span data-stu-id="7d766-109">Containers therefore have a much smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="7d766-110">每个容器可以运行整个 web 应用程序或服务，图 1-1 中所示。</span><span class="sxs-lookup"><span data-stu-id="7d766-110">Each container can run a whole web application or a service, as shown in Figure 1-1.</span></span> <span data-ttu-id="7d766-111">在此示例中，Docker 主机是容器主机，而 App1、 App2、 Svc1 和 Svc2 是容器化应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="7d766-111">In this example, Docker host is a container host, and App1, App2, Svc1, and Svc2 are containerized applications or services.</span></span>

![两个应用程序和两个 VM 或物理服务器的操作系统上运行的服务](./media/image1.png)

<span data-ttu-id="7d766-113">**图 1-1**。</span><span class="sxs-lookup"><span data-stu-id="7d766-113">**Figure 1-1**.</span></span> <span data-ttu-id="7d766-114">在一个容器主机上运行多个容器</span><span class="sxs-lookup"><span data-stu-id="7d766-114">Multiple containers running on a container host</span></span>

<span data-ttu-id="7d766-115">可从容器化获得的另一个优势是可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="7d766-115">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="7d766-116">通过为短期任务创建新容器，可以快速扩大。</span><span class="sxs-lookup"><span data-stu-id="7d766-116">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="7d766-117">从应用程序的角度来看，实例化映像（创建容器）类似于实例化 服务或 Web 应用等进程。</span><span class="sxs-lookup"><span data-stu-id="7d766-117">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="7d766-118">但出于可靠性考虑，在多个主机服务器上运行同一映像的多个实例时，通常要使每个容器（映像实例）在不同容错域中的不同主机服务器或 VM 中运行。</span><span class="sxs-lookup"><span data-stu-id="7d766-118">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="7d766-119">简单地说，容器提供隔离、 可移植性、 灵活性、 可缩放性和控制的优势跨整个应用程序生命周期工作流。</span><span class="sxs-lookup"><span data-stu-id="7d766-119">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application lifecycle workflow.</span></span> <span data-ttu-id="7d766-120">最重要的好处是 Dev 和 Ops 之间提供环境隔离。</span><span class="sxs-lookup"><span data-stu-id="7d766-120">The most important benefit is the environment isolation provided between Dev and Ops.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="7d766-121">下一页</span><span class="sxs-lookup"><span data-stu-id="7d766-121">Next</span></span>](what-is-docker.md)
