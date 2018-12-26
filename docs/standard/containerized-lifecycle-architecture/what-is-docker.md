---
title: 什么是 Docker？
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 360a404e38651b78acc3a52d8102a4dae71f3e30
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152703"
---
# <a name="what-is-docker"></a><span data-ttu-id="35c3c-103">什么是 Docker？</span><span class="sxs-lookup"><span data-stu-id="35c3c-103">What is Docker?</span></span>

<span data-ttu-id="35c3c-104">[Docker](https://www.docker.com/)是一个[开源项目](https://github.com/docker/docker)，用于将应用程序自动部署为可移植，自给自足的容器，可以在云或本地运行（参见图1-2）。</span><span class="sxs-lookup"><span data-stu-id="35c3c-104">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run in the cloud or on-premises (see Figure 1-2).</span></span> <span data-ttu-id="35c3c-105">Docker也是一家推广和开发这项技术的[公司](https://www.docker.com/)，与包括微软在内的云，Linux和Windows供应商合作。</span><span class="sxs-lookup"><span data-stu-id="35c3c-105">Docker is also a [company](https://www.docker.com/) that promotes and develops this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![](./media/image2.png)

<span data-ttu-id="35c3c-106">图 1-2:Docker 在混合云的所有层部署容器</span><span class="sxs-lookup"><span data-stu-id="35c3c-106">Figure 1-2: Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="35c3c-107">Docker 镜像容器可以在 Linux 和 Windows 上原生运行。</span><span class="sxs-lookup"><span data-stu-id="35c3c-107">Docker image containers can run natively on Linux and Windows.</span></span> <span data-ttu-id="35c3c-108">但是，Windows 映像只能在 Windows 主机上运行，而 Linux 映像只能在 Linux 主机上运行，作为主机服务器或VM。</span><span class="sxs-lookup"><span data-stu-id="35c3c-108">However, Windows images can run only on Windows hosts and Linux images can run only on Linux hosts, meaning a host server or a VM.</span></span>

<span data-ttu-id="35c3c-109">开发人员可以在 Windows、Linux 或 macOS 上使用开发环境。</span><span class="sxs-lookup"><span data-stu-id="35c3c-109">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="35c3c-110">在开发计算机上，开发人员在运行到哪个 Docker 映像部署，包括应用程序和其依赖项的 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="35c3c-110">On the development computer, the developer runs a Docker host to which Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="35c3c-111">在 Linux 或 Mac 上进行开发的开发人员使用基于 Linux 的 Docker 主机，并且他们可以仅为 Linux 容器创建映像。</span><span class="sxs-lookup"><span data-stu-id="35c3c-111">Developers who work on Linux or on the Mac use a Docker host that is Linux based, and they can create images only for Linux containers.</span></span> <span data-ttu-id="35c3c-112">(在 Mac 上工作的开发人员可以编辑代码或运行 Docker 命令行接口\[CLI\]从 macOS，但是，在撰写本文时，容器不直接在 macOS 上运行。)在 Windows 上进行开发的开发人员可以为 Linux 或 Windows 容器创建映像。</span><span class="sxs-lookup"><span data-stu-id="35c3c-112">(Developers working on the Mac can edit code or run the Docker command-line interface \[CLI\] from macOS, but, as of this writing, containers do not run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="35c3c-113">为了在开发环境中托管容器，并提供其他开发人员工具，Docker 为 Windows 或 macOS 提供了 [Docker 社区版 (CE)](https://www.docker.com/community-edition)。</span><span class="sxs-lookup"><span data-stu-id="35c3c-113">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="35c3c-114">这些产品安装了托管容器所需的 VM（Docker 主机）。</span><span class="sxs-lookup"><span data-stu-id="35c3c-114">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="35c3c-115">Docker 还提供 [Docker 企业版 (EE)](https://www.docker.com/enterprise-edition)，该版本专为企业开发而设计，供生成、交付和在生产中运行大型业务关键型应用程序的 IT 团队使用。</span><span class="sxs-lookup"><span data-stu-id="35c3c-115">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="35c3c-116">若要运行 [Windows 容器](/virtualization/windowscontainers/about/)，有两种类型的运行时可供使用：</span><span class="sxs-lookup"><span data-stu-id="35c3c-116">To run [Windows Containers](/virtualization/windowscontainers/about/), there are two types of runtimes:</span></span>

-   <span data-ttu-id="35c3c-117">**Windows Server 容器** 此运行时通过进程和名称空间隔离技术提供应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="35c3c-117">**Windows Server Container** This runtime provides application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="35c3c-118">Windows Server 容器与容器主机和主机上运行的所有容器共享内核。</span><span class="sxs-lookup"><span data-stu-id="35c3c-118">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

-   <span data-ttu-id="35c3c-119">**HYPER-V 容器** 这会提供由 Windows Server 容器通过在高度优化的 VM 中运行每个容器的隔离上扩展。</span><span class="sxs-lookup"><span data-stu-id="35c3c-119">**Hyper-V Container** This expands on the isolation provided by Windows Server Containers by running each container in a highly optimized VM.</span></span> <span data-ttu-id="35c3c-120">在此配置中，容器主机的内核不与 Hyper-V 容器共享，以提供更好地隔离。</span><span class="sxs-lookup"><span data-stu-id="35c3c-120">In this configuration, the kernel of the container host is not shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="35c3c-121">这些容器的映像以相同的方式创建并且功能相同。</span><span class="sxs-lookup"><span data-stu-id="35c3c-121">The images for these containers are created in the same way and function the same.</span></span> <span data-ttu-id="35c3c-122">区别在于如何从映像创建容器-运行 HYPER-V 容器需要一个额外的参数。</span><span class="sxs-lookup"><span data-stu-id="35c3c-122">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="35c3c-123">有关详细信息，请参阅 [Hyper-V 容器](/virtualization/windowscontainers/about/)。</span><span class="sxs-lookup"><span data-stu-id="35c3c-123">For details, see [Hyper-V Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="comparing-docker-containers-with-vms"></a><span data-ttu-id="35c3c-124">比较 Docker 容器和 Vm</span><span class="sxs-lookup"><span data-stu-id="35c3c-124">Comparing Docker containers with VMs</span></span>

<span data-ttu-id="35c3c-125">图 1-3 显示了 VM 和 Docker 容器之间的比较</span><span class="sxs-lookup"><span data-stu-id="35c3c-125">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

<span data-ttu-id="35c3c-126">由于容器需要的资源少得多（例如，它们不需要完整的操作系统），因此它们易于部署并且启动速度快。</span><span class="sxs-lookup"><span data-stu-id="35c3c-126">Because containers require far fewer resources (for example, they do not need a full OS), they are easy to deploy and they start fast.</span></span> <span data-ttu-id="35c3c-127">这使您可以拥有更高的密度，这意味着您可以在同一硬件单元上运行更多服务，从而降低成本。</span><span class="sxs-lookup"><span data-stu-id="35c3c-127">This makes it possible for you to have higher density, meaning that you can run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="35c3c-128">作为在同一内核上运行的副作用，您实现的隔离比VM少。</span><span class="sxs-lookup"><span data-stu-id="35c3c-128">As a side effect of running on the same kernel, you achieve less isolation than VMs.</span></span>

<span data-ttu-id="35c3c-129">映像的主要目标是使环境（依赖项）在不同的部署中保持不变。</span><span class="sxs-lookup"><span data-stu-id="35c3c-129">The main goal of an image is that it makes the environment (dependencies) the same across different deployments.</span></span> <span data-ttu-id="35c3c-130">这意味着您可以在计算机上对其进行调试，然后将其部署到保证具有相同环境的另一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="35c3c-130">This means that you can debug it on your machine and then deploy it to another machine with the same environment guaranteed.</span></span>

<span data-ttu-id="35c3c-131">容器映像是一种打包应用程序或服务并以可靠且可重现的方式部署它的方法。</span><span class="sxs-lookup"><span data-stu-id="35c3c-131">A container image is a way to package an app or service and deploy it in a reliable and reproducible manner.</span></span> <span data-ttu-id="35c3c-132">在这方面，Docker 不仅是一种技术，它也是一种理念和过程。</span><span class="sxs-lookup"><span data-stu-id="35c3c-132">In this respect, Docker is not only a technology, it's also a philosophy and a process.</span></span>

<span data-ttu-id="35c3c-133">使用 Docker 时，您将听不到开发人员说，"适用于我的计算机，为什么不在生产环境中？"</span><span class="sxs-lookup"><span data-stu-id="35c3c-133">When using Docker, you will not hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="35c3c-134">他们可以只是说，"它在 Docker 上运行，"因为打包的 Docker 应用程序可以在任何受支持的 Docker 环境上运行，并且它将重新运行安装程序对所有部署目标 （开发、 QA、 暂存、 生产等。） 使用的方式运行。</span><span class="sxs-lookup"><span data-stu-id="35c3c-134">They can simply say, "It runs on Docker," because the packaged Docker application can be run on any supported Docker environment, and it will run the way it was intended to on all deployment destinations (Dev, QA, staging, production, etc.).</span></span>

![](./media/image3.png)

<span data-ttu-id="35c3c-135">图 1-3:传统 Vm 到 Docker 容器的比较</span><span class="sxs-lookup"><span data-stu-id="35c3c-135">Figure 1-3: Comparison of traditional VMs to Docker containers</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="35c3c-136">[上一页](index.md)
>[下一页](docker-terminology.md)</span><span class="sxs-lookup"><span data-stu-id="35c3c-136">[Previous](index.md)
[Next](docker-terminology.md)</span></span>