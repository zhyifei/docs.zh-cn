---
title: 什么是 Docker？
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c471c4bc1588aaa6c0e145ede0b67ab5340f254a
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="what-is-docker"></a><span data-ttu-id="6b8ad-103">什么是 Docker？</span><span class="sxs-lookup"><span data-stu-id="6b8ad-103">What is Docker?</span></span>

<span data-ttu-id="6b8ad-104">[Docker](https://www.docker.com/)是[开放源代码项目](https://github.com/docker/docker)用于自动执行与可以在云或本地运行的可移植的足容器应用程序的部署 (请参阅图 1-2）。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-104">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run in the cloud or on-premises (see Figure 1-2).</span></span> <span data-ttu-id="6b8ad-105">Docker 也是[公司](https://www.docker.com/)，推广并制定此技术，在与云，Linux 和 Windows 供应商，包括 Microsoft 协作中工作。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-105">Docker is also a [company](https://www.docker.com/) that promotes and develops this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![](./media/image2.png)

<span data-ttu-id="6b8ad-106">图 1-2: Docker 部署在混合云中的所有层的容器</span><span class="sxs-lookup"><span data-stu-id="6b8ad-106">Figure 1-2: Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="6b8ad-107">Docker 映像容器可以本机 Linux 和 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-107">Docker image containers can run natively on Linux and Windows.</span></span> <span data-ttu-id="6b8ad-108">但是，Windows 映像可以仅在 Windows 主机上运行，并且可以仅在 Linux 主机，这意味着主机服务器或 VM 上运行 Linux 映像。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-108">However, Windows images can run only on Windows hosts and Linux images can run only on Linux hosts, meaning a host server or a VM.</span></span>

<span data-ttu-id="6b8ad-109">开发人员可以在 Windows、 Linux 或 macOS 上使用开发环境。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-109">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="6b8ad-110">在开发计算机上开发人员运行到的 Docker 映像部署，包括应用程序和其依赖项的 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-110">On the development computer, the developer runs a Docker host to which Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="6b8ad-111">开发人员在 Linux 上或在 Mac 上工作使用基于，Linux 的 Docker 主机，它们可以创建仅针对 Linux 容器映像。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-111">Developers who work on Linux or on the Mac use a Docker host that is Linux based, and they can create images only for Linux containers.</span></span> <span data-ttu-id="6b8ad-112">(在 Mac 上工作的开发人员可以编辑代码或运行 Docker 命令行界面\[CLI\]从 macOS，但是，撰写本文时，容器不直接在 macOS 上运行。)在 Windows 处理开发人员可以为 Linux 或 Windows 容器创建映像。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-112">(Developers working on the Mac can edit code or run the Docker command-line interface \[CLI\] from macOS, but, as of this writing, containers do not run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="6b8ad-113">若要承载在开发环境中的容器，并提供其他开发人员工具，Docker 附带[Docker 社区版 (CE)](https://www.docker.com/community-edition)为 Windows 或 macOS。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-113">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="6b8ad-114">这些产品安装需要的 VM （Docker 主机） 来承载容器。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-114">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="6b8ad-115">Docker 还可提供[Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition)、 其用于企业开发，由 IT 团队生成、 装运，，和在生产中运行大型业务关键型应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-115">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="6b8ad-116">若要运行[Windows 容器](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)，有两种类型的运行时：</span><span class="sxs-lookup"><span data-stu-id="6b8ad-116">To run [Windows Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview), there are two types of runtimes:</span></span>

-   <span data-ttu-id="6b8ad-117">**Windows Server 容器** 此运行时提供通过进程和命名空间隔离技术的应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-117">**Windows Server Container** This runtime provides application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="6b8ad-118">Windows Server 容器与容器主机和主机上运行的所有容器共享内核。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-118">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

-   <span data-ttu-id="6b8ad-119">**HYPER-V 容器** 这会将对由 Windows Server 容器通过在高度优化的 VM 中运行每个容器提供的隔离上扩展。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-119">**Hyper-V Container** This expands on the isolation provided by Windows Server Containers by running each container in a highly optimized VM.</span></span> <span data-ttu-id="6b8ad-120">在此配置中，容器主机的内核不与 Hyper-V 容器共享，以提供更好地隔离。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-120">In this configuration, the kernel of the container host is not shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="6b8ad-121">适用于这些容器的映像的创建相同的方式和功能相同。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-121">The images for these containers are created in the same way and function the same.</span></span> <span data-ttu-id="6b8ad-122">区别在于如何从映像创建容器-运行 HYPER-V 容器需要使用额外的参数。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-122">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="6b8ad-123">有关详细信息，请参阅 [Hyper-V 容器](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-123">For details, see [Hyper-V Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).</span></span>

## <a name="comparing-docker-containers-with-vms"></a><span data-ttu-id="6b8ad-124">比较与 Vm 的 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="6b8ad-124">Comparing Docker containers with VMs</span></span>

<span data-ttu-id="6b8ad-125">图 1-3 显示的比较虚拟机和 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-125">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

<span data-ttu-id="6b8ad-126">因为容器需要数量少得多的资源 （例如，它们不需要完整的 OS），因此可以轻松部署和快速启动。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-126">Because containers require far fewer resources (for example, they do not need a full OS), they are easy to deploy and they start fast.</span></span> <span data-ttu-id="6b8ad-127">这使你能够更高的密度，这意味着，你可以在相同的硬件单元，从而降低成本上运行更多的服务。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-127">This makes it possible for you to have higher density, meaning that you can run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="6b8ad-128">在同一个内核上运行的副作用是，为你实现比 Vm 较少隔离。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-128">As a side effect of running on the same kernel, you achieve less isolation than VMs.</span></span>

<span data-ttu-id="6b8ad-129">映像的主要目标是使环境（依赖项）在不同的部署中保持不变。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-129">The main goal of an image is that it makes the environment (dependencies) the same across different deployments.</span></span> <span data-ttu-id="6b8ad-130">也就是说，可以在计算机上调试它，然后将其部署到保证具有相同环境的另一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-130">This means that you can debug it on your machine and then deploy it to another machine with the same environment guaranteed.</span></span>

<span data-ttu-id="6b8ad-131">容器映像是一种方法来打包的应用或服务并将其部署以可靠且可重现的方式。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-131">A container image is a way to package an app or service and deploy it in a reliable and reproducible manner.</span></span> <span data-ttu-id="6b8ad-132">在这一方面，Docker 不是仅一种技术，也是基本原理和进程。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-132">In this respect, Docker is not only a technology, it's also a philosophy and a process.</span></span>

<span data-ttu-id="6b8ad-133">当使用 Docker，您将无法听到开发人员说，"It works 我在计算机上，不要在生产中？"</span><span class="sxs-lookup"><span data-stu-id="6b8ad-133">When using Docker, you will not hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="6b8ad-134">他们可以简单地说，"上运行 Docker，"因为打包的 Docker 应用程序可以运行任何受支持的 Docker 环境，并且它将重新运行安装程序为所有部署目标 （开发、 QA、 过渡，生产等。） 使用的方式运行。</span><span class="sxs-lookup"><span data-stu-id="6b8ad-134">They can simply say, "It runs on Docker," because the packaged Docker application can be run on any supported Docker environment, and it will run the way it was intended to on all deployment destinations (Dev, QA, staging, production, etc.).</span></span>

![](./media/image3.png)

<span data-ttu-id="6b8ad-135">图 1-3： 的传统 Vm 到 Docker 容器的比较</span><span class="sxs-lookup"><span data-stu-id="6b8ad-135">Figure 1-3: Comparison of traditional VMs to Docker containers</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6b8ad-136">[上一页] (index.md) [下一页] (docker-terminology.md)</span><span class="sxs-lookup"><span data-stu-id="6b8ad-136">[Previous] (index.md) [Next] (docker-terminology.md)</span></span>
