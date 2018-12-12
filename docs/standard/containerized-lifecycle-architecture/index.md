---
title: 容器和 Docker 简介
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: c2a6b9802bbb995939d33c5c40ef9c1afa1620e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148816"
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="8abc9-103">容器和 Docker 简介</span><span class="sxs-lookup"><span data-stu-id="8abc9-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="8abc9-104">容器化是软件开发的一种方法，通过该方法可将应用程序或服务、其依赖项及其配置（抽象化为部署清单文件）一起打包为容器映像。</span><span class="sxs-lookup"><span data-stu-id="8abc9-104">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="8abc9-105">然后可将容器化应用程序作为单元进行测试，并将其作为容器映像实例部署到主机操作系统。</span><span class="sxs-lookup"><span data-stu-id="8abc9-105">You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system.</span></span>

<span data-ttu-id="8abc9-106">就像运输业借助船只、火车或卡车运输使用标准化容器运输货物而不论其内部的货物一样，软件容器充当软件的标准单位，其中可以包含不同的代码和依赖项。</span><span class="sxs-lookup"><span data-stu-id="8abc9-106">Just as the shipping industry uses standardized containers to move goods by ship, train, or truck, regardless of the cargo within them, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="8abc9-107">将软件放入容器，让开发人员和 IT 专业人士只需进行极少修改或无需修改，即可将这些容器部署到不同环境。</span><span class="sxs-lookup"><span data-stu-id="8abc9-107">Placing software into containers makes it possible for developers and IT professionals to deploy those containers across environments with little or no modification.</span></span>

<span data-ttu-id="8abc9-108">容器还会在共享操作系统 (OS) 上将应用程序彼此隔离开。</span><span class="sxs-lookup"><span data-stu-id="8abc9-108">Containers also isolate applications from one another on a shared operating system (OS).</span></span> <span data-ttu-id="8abc9-109">容器化应用程序在容器主机上运行，而容器主机在 OS（Linux 或 Windows）上运行。</span><span class="sxs-lookup"><span data-stu-id="8abc9-109">Containerized applications run on top of a container host, which in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="8abc9-110">因此，容器的占用比虚拟机 (VM) 映像小得多。</span><span class="sxs-lookup"><span data-stu-id="8abc9-110">Thus, containers have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="8abc9-111">每个容器可以运行整个 Web 应用或服务，如图 1-1 所示。</span><span class="sxs-lookup"><span data-stu-id="8abc9-111">Each container can run an entire web application or a service, as shown in Figure 1-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="8abc9-112">图 1-1:在一个容器主机上运行多个容器</span><span class="sxs-lookup"><span data-stu-id="8abc9-112">Figure 1-1: Multiple containers running on a container host</span></span>

<span data-ttu-id="8abc9-113">在此示例中，Docker 主机是容器主机，而 App 1、App 2、Svc 1 和 Svc 2 是容器化应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="8abc9-113">In this example, Docker Host is a container host, and App 1, App 2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

<span data-ttu-id="8abc9-114">可从容器化获得的另一个优势是可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="8abc9-114">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="8abc9-115">通过为短期任务创建新容器，可以快速横向扩展。</span><span class="sxs-lookup"><span data-stu-id="8abc9-115">You can scale-out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="8abc9-116">从应用程序的角度来看，实例化映像（创建容器）类似于实例化服务或 Web 应用等进程。</span><span class="sxs-lookup"><span data-stu-id="8abc9-116">From an application point of view, *instantiating an image* (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="8abc9-117">出于可靠性考虑，但是，跨多个主机服务器，运行同一映像的多个实例时您通常希望每个容器 （映像实例） 在不同主机服务器中运行或在不同的容错域中的 VM。</span><span class="sxs-lookup"><span data-stu-id="8abc9-117">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="8abc9-118">总而言之，容器在整个应用程序生命周期工作流中提供以下优点：隔离性、可移植性、灵活性、可伸缩性和可控性。</span><span class="sxs-lookup"><span data-stu-id="8abc9-118">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application life cycle workflow.</span></span> <span data-ttu-id="8abc9-119">最重要的优点是可在开发和操作之间提供隔离。</span><span class="sxs-lookup"><span data-stu-id="8abc9-119">The most important benefit is the isolation provided between Dev and Ops.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="8abc9-120">下一页</span><span class="sxs-lookup"><span data-stu-id="8abc9-120">Next</span></span>](what-is-docker.md)